# No Title

**Source:** https://docs.n8n.io/_workflows//courses/level-one/chapter-5/chapter-5.3.json

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
340,
-680
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
"value": "tblo2KuMyn5X4jU0s",
"mode": "list",
"cachedResultName": "orders"
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
"id": "customerID",
"displayName": "customerID",
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
},
{
"id": "orderPrice",
"displayName": "orderPrice",
"required": false,
"defaultMatch": false,
"canBeUsedToMatch": true,
"display": true,
"type": "number",
"readOnly": false,
"removed": false
},
{
"id": "orderStatus",
"displayName": "orderStatus",
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
800,
-680
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
540,
-680
],
"id": "70e4db65-f827-4e4f-8673-b405b7986d6e",
"name": "If1"
},
{
"parameters": {},
"type": "n8n-nodes-base.manualTrigger",
"typeVersion": 1,
"position": [
140,
-680
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
"node": "Airtable1",
"type": "main",
"index": 0
}
],
[]
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
