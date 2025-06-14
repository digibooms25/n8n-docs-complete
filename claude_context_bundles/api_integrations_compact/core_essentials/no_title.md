# No Title

**Source:** https://docs.n8n.io/_workflows/try-it-out/quickstart/tutorial.json

---

{
"name": "Tutorial-workflow",
"nodes": [
{
"parameters": {
"rule": {
"interval": [
{
"field": "weeks",
"triggerAtDay": [
],
"triggerAtHour": 9
}
]
}
},
"type": "n8n-nodes-base.scheduleTrigger",
"typeVersion": 1.2,
"position": [
-680,
],
"id": "ef14445c-2f5f-4c78-96c8-66732feb7a8f",
"name": "Schedule Trigger"
},
{
"parameters": {
"resource": "donkiSolarFlare",
"additionalFields": {
"startDate": "={{ $today.minus(7, 'days') }}"
}
},
"type": "n8n-nodes-base.nasa",
"typeVersion": 1,
"position": [
-460,
],
"id": "52c58b93-c780-4aff-a216-d67b28195a45",
"name": "NASA",
"credentials": {
"nasaApi": {
"id": "sSVnxV9AcBmBOYn8",
"name": "NASA account"
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
"id": "2f469c8e-12b3-4ee5-95fc-ff81508d0b43",
"leftValue": "={{ $json.classType }}",
"rightValue": "C",
"operator": {
"type": "string",
"operation": "contains"
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
-240,
],
"id": "b54e3289-9ebb-451f-8bac-87edeeeced13",
"name": "If"
},
{
"parameters": {
"resource": "request",
"operation": "send",
"binId": "1741914338605-0907339996192",
"binContent": "=There was a solar flare of class {{$json[\"classType\"]}}",
"requestOptions": {}
},
"type": "n8n-nodes-base.postBin",
"typeVersion": 1,
"position": [
-20,
],
"id": "a8b602b6-17b1-4274-8d33-73344b6bb8fb",
"name": "PostBin(true)"
},
{
"parameters": {
"resource": "request",
"operation": "send",
"binId": "1741914338605-0907339996192",
"binContent": "=There was a solar flare of class {{$json[\"classType\"]}}",
"requestOptions": {}
},
"type": "n8n-nodes-base.postBin",
"typeVersion": 1,
"position": [
-20,
],
"id": "09c2c7a4-c229-430d-a5b0-8d7491515d9f",
"name": "PostBin(false)"
},
{
"parameters": {
"content": "## Setup required\n\nYou need to create a NASA account and create credentials, and create a bin with Postbin and enter the ID - see [the documentation](https://docs.n8n.io/try-it-out/longer-introduction/)",
"height": 120,
"width": 600
},
"type": "n8n-nodes-base.stickyNote",
"typeVersion": 1,
"position": [
-720,
],
"id": "08e0b8f9-c90e-4c9c-a663-01aca805b9be",
"name": "Sticky Note"
}
],
"pinData": {},
"connections": {
"Schedule Trigger": {
"main": [
[
{
"node": "NASA",
"type": "main",
"index": 0
}
]
]
},
"NASA": {
"main": [
[
{
"node": "If",
"type": "main",
"index": 0
}
]
]
},
"If": {
"main": [
[
{
"node": "PostBin(true)",
"type": "main",
"index": 0
}
],
[
{
"node": "PostBin(false)",
"type": "main",
"index": 0
}
]
]
}
},
"active": false,
"settings": {
"executionOrder": "v1"
},
"versionId": "37de4877-e4f6-4b9a-b6f0-9b7e7aea0163",
"meta": {
"templateCredsSetupCompleted": true,
"instanceId": "cb484ba7b742928a2048bf8829668bed5b5ad9787579adea888f05980292a4a7"
},
"id": "DPzMzTIyDrYohiw4",
"tags": [
{
"createdAt": "2021-06-25T07:47:07.640Z",
"updatedAt": "2021-06-25T07:47:07.640Z",
"id": "1",
"name": "docs"
}
]
}
