# No Title

**Source:** https://docs.n8n.io/_workflows/integrations/builtin/core-nodes/n8n-nodes-base.extractfromfile/webhook-example.json

---

{
"name": "Extract from file example",
"nodes": [
{
"parameters": {
"httpMethod": "POST",
"path": "06696ea7-9dc7-464a-873b-3feb095b0874",
"options": {
"rawBody": true
}
},
"type": "n8n-nodes-base.webhook",
"typeVersion": 2,
"position": [
-380,
],
"id": "dfbd51af-6050-47c5-a26c-74cba77f65f7",
"name": "Webhook",
"webhookId": "06696ea7-9dc7-464a-873b-3feb095b0874"
},
{
"parameters": {
"options": {
"headerRow": false
}
},
"type": "n8n-nodes-base.extractFromFile",
"typeVersion": 1,
"position": [
-160,
],
"id": "1b1e4643-8269-402b-83af-dfd90fd6a0b5",
"name": "Extract from File"
}
],
"pinData": {},
"connections": {
"Webhook": {
"main": [
[
{
"node": "Extract from File",
"type": "main",
"index": 0
}
]
]
}
},
"active": true,
"settings": {
"executionOrder": "v1"
},
"versionId": "dd2bf7f1-692a-41a8-9c2e-7931de57fa13",
"meta": {
"instanceId": "1060f46e51fc7902c377ab29d7cbfb87696ddf6b3c5c27cbbb65c3cb36e21baf"
},
"id": "9i3iDZf5MpjlJ2sh",
"tags": []
}
