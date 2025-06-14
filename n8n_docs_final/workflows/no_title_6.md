# No Title

**Source:** https://docs.n8n.io/_workflows//courses/level-one/chapter-5/chapter-5.6.json

---

{
"nodes": [
{
"parameters": {
"url": "https://internal.users.n8n.cloud/webhook/custom-erp",
"authentication": "genericCredentialType",
"genericAuthType": "httpHeaderAuth",
"sendHeaders": true,
"headerParameters": {
"parameters": [
{
"name": "unique_id",
"value": ""
}
]
},
"options": {}
},
"type": "n8n-nodes-base.httpRequest",
"typeVersion": 4.2,
"position": [
300,
-520
],
"id": "ada6becf-c320-41a7-bdca-a842ea3ee769",
"name": "HTTP Request1",
"credentials": {
"httpHeaderAuth": {
"id": "sMuanZ4xGobAurzY",
"name": "Nathan's ABCorp data warehouse account"
}
}
},
{
"parameters": {
"operation": "create",
"base": {
"__rl": true,
"value": "app9nOVsRxdypoknP",
"mode": "list",
"cachedResultName": "beginner course"
},
"table": {
"__rl": true,
"value": "tblTIOsm4BLJD9Tql",
"mode": "list",
"cachedResultName": "processingOrders"
},
"columns": {
"mappingMode": "autoMapInputData",
"value": {},
"matchingColumns": [],
"schema": [
{
"id": "orderID",
"displayName": "orderID",
"required": false,
"defaultMatch": false,
"canBeUsedToMatch": true,
"display": true,
"type": "number",
"readOnly": false,
"removed": false
},
{
"id": "employeeName",
"displayName": "employeeName",
"required": false,
"defaultMatch": false,
"canBeUsedToMatch": true,
"display": true,
"type": "string",
"readOnly": false,
"removed": false
}
],
"attemptToConvertTypes": false,
"convertFieldsToString": false
},
"options": {}
},
"type": "n8n-nodes-base.airtable",
"typeVersion": 2.1,
"position": [
1020,
-600
],
"id": "5e60ca72-d773-439c-b39a-4b14c54f795b",
"name": "Airtable1",
"credentials": {
"airtableTokenApi": {
"id": "UT32NHUYnp4pn1H3",
"name": "Airtable Personal Access Token account"
}
}
},
{
"parameters": {
"conditions": {
"options": {
"caseSensitive": true,
"leftValue": "",
"typeValidation": "strict",
"version": 2
},
"conditions": [
{
"id": "526cb30c-0f90-4f66-8f98-b64ceb2e52f2",
"leftValue": "={{ $json.orderStatus }}",
"rightValue": "processing",
"operator": {
"type": "string",
"operation": "equals"
}
}
],
"combinator": "and"
},
"options": {}
},
"type": "n8n-nodes-base.if",
"typeVersion": 2.2,
"position": [
520,
-520
],
"id": "70e4db65-f827-4e4f-8673-b405b7986d6e",
"name": "If1"
},
{
"parameters": {
"assignments": {
"assignments": [
{
"id": "20d37948-763a-4d7b-b725-e65f3802af03",
"name": "orderID",
"value": "={{ $json.orderID }}",
"type": "number"
},
{
"id": "9df108a7-6b13-42ab-a6dd-9ca582ba8b49",
"name": "employeeName",
"value": "={{ $json.employeeName }}",
"type": "string"
}
]
},
"options": {}
},
"type": "n8n-nodes-base.set",
"typeVersion": 3.4,
"position": [
800,
-600
],
"id": "a3d3dc53-32f1-4f44-bf95-50bc5450d601",
"name": "Edit Fields1"
},
{
"parameters": {
"jsCode": "let items = $input.all();\nlet totalBooked = items.length;\nlet bookedSum = 0;\n\nfor (let i=0; i < items.length; i++) {\n bookedSum = bookedSum + items[i].json.orderPrice;\n}\n\nreturn [{ json: {totalBooked, bookedSum} }];"
},
"type": "n8n-nodes-base.code",
"typeVersion": 2,
"position": [
760,
-420
],
"id": "d24ea5e9-c9e6-4d06-b6ee-8db1abd42bc0",
"name": "Code1"
},
{
"parameters": {
"authentication": "webhook",
"content": "=This week we've {{$json[\"totalBooked\"]}} booked orders with a total value of {{$json[\"bookedSum\"]}}. My Unique ID: {{ $('HTTP Request1').params[\"headerParameters\"][\"parameters\"][0][\"value\"] }}",
"options": {}
},
"type": "n8n-nodes-base.discord",
"typeVersion": 2,
"position": [
1000,
-420
],
"id": "ed380465-c655-4c38-8eb3-2008b9e7869f",
"name": "Discord1",
"webhookId": "eff0b651-f0be-4cae-8f18-7d831385be3c",
"credentials": {
"discordWebhookApi": {
"id": "lOieo0mIb6h1Wi9R",
"name": "Discord Webhook account"
}
}
},
{
"parameters": {},
"type": "n8n-nodes-base.manualTrigger",
"typeVersion": 1,
"position": [
80,
-520
],
"id": "ffa1a8ce-1a1e-48c4-8a0d-6af28c0447a5",
"name": "When clicking ‘Execute workflow’"
}
],
"connections": {
"HTTP Request1": {
"main": [
[
{
"node": "If1",
"type": "main",
"index": 0
}
]
]
},
"If1": {
"main": [
[
{
"node": "Edit Fields1",
"type": "main",
"index": 0
}
],
[
{
"node": "Code1",
"type": "main",
"index": 0
}
]
]
},
"Edit Fields1": {
"main": [
[
{
"node": "Airtable1",
"type": "main",
"index": 0
}
]
]
},
"Code1": {
"main": [
[
{
"node": "Discord1",
"type": "main",
"index": 0
}
]
]
},
"When clicking ‘Execute workflow’": {
"main": [
[
{
"node": "HTTP Request1",
"type": "main",
"index": 0
}
]
]
}
},
"pinData": {},
"meta": {
"templateCredsSetupCompleted": true,
"instanceId": "24789c4d5aa56ca018d140332e7a43fd37dd7af0409453314fff12dc1aeebfa8"
}
}
