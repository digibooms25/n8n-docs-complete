# No Title

**Source:** https://docs.n8n.io/_workflows/integrations/builtin/app-nodes/n8n-nodes-base.googledrive/get-most-recent-file.json

---

{
"meta": {
"instanceId": "cb484ba7b742928a2048bf8829668bed5b5ad9787579adea888f05980292a4a7"
},
"nodes": [
{
"parameters": {
"operation": "download",
"fileId": {
"__rl": true,
"value": "={{ $json.id }}",
"mode": "id"
},
"options": {}
},
"id": "45b53bcd-7dcf-4266-8b6e-bfc12008f9e2",
"name": "Google Drive1",
"type": "n8n-nodes-base.googleDrive",
"typeVersion": 3,
"position": [
1500,
]
},
{
"parameters": {},
"id": "ba223e7c-4fed-41dd-8c80-2e8fd742629f",
"name": "When clicking ‘Execute workflow’",
"type": "n8n-nodes-base.manualTrigger",
"typeVersion": 1,
"position": [
620,
]
},
{
"parameters": {
"resource": "fileFolder",
"searchMethod": "query",
"returnAll": true,
"filter": {
"whatToSearch": "files"
},
"options": {
"fields": [
"*"
]
}
},
"id": "42799909-16f3-4f0a-9ad9-4dd0375814a0",
"name": "Google Drive",
"type": "n8n-nodes-base.googleDrive",
"typeVersion": 3,
"position": [
840,
]
},
{
"parameters": {
"sortFieldsUi": {
"sortField": [
{
"fieldName": "modifiedTime",
"order": "descending"
}
]
},
"options": {}
},
"id": "bfb8baa6-1b8c-4540-9ad6-b5d7c3f7521b",
"name": "Sort",
"type": "n8n-nodes-base.sort",
"typeVersion": 1,
"position": [
1060,
]
},
{
"parameters": {},
"id": "2883d39a-f7d9-4244-bf7d-b06878678ccc",
"name": "Limit",
"type": "n8n-nodes-base.limit",
"typeVersion": 1,
"position": [
1280,
]
}
],
"connections": {
"When clicking ‘Execute workflow’": {
"main": [
[
{
"node": "Google Drive",
"type": "main",
"index": 0
}
]
]
},
"Google Drive": {
"main": [
[
{
"node": "Sort",
"type": "main",
"index": 0
}
]
]
},
"Sort": {
"main": [
[
{
"node": "Limit",
"type": "main",
"index": 0
}
]
]
},
"Limit": {
"main": [
[
{
"node": "Google Drive1",
"type": "main",
"index": 0
}
]
]
}
},
"pinData": {}
}
