# No Title

**Source:** https://docs.n8n.io/_workflows/integrations/builtin/core-nodes/n8n-nodes-base.splitinbatches/rss-feed-example.json

---

{
"nodes": [
{
"parameters": {},
"type": "n8n-nodes-base.manualTrigger",
"typeVersion": 1,
"position": [
0,
],
"id": "e6e1cfe6-eff1-48bd-b21c-6ba83d4244d9",
"name": "When clicking ‘Execute workflow’"
},
{
"parameters": {
"jsCode": "return [\n\t{\n\t\tjson: {\n\t\t\turl: 'https://medium.com/feed/n8n-io',\n\t\t}\n\t},\n\t{\n\t\tjson: {\n\t\t\turl: 'https://dev.to/feed/n8n',\n\t\t}\n\t}\n];"
},
"type": "n8n-nodes-base.code",
"typeVersion": 2,
"position": [
220,
],
"id": "137f1128-45b6-4bc4-a9fb-8660baa652a9",
"name": "Code"
},
{
"parameters": {
"options": {}
},
"type": "n8n-nodes-base.splitInBatches",
"typeVersion": 3,
"position": [
440,
],
"id": "3449a953-49c2-4a36-ba3d-cbc0573f3f6c",
"name": "Loop Over Items"
},
{
"parameters": {
"url": "={{ $json.url }}",
"options": {}
},
"type": "n8n-nodes-base.rssFeedRead",
"typeVersion": 1.1,
"position": [
660,
],
"id": "cc2e59d7-0a9b-4640-8052-d8f7f8d8c9fe",
"name": "RSS Read"
}
],
"connections": {
"When clicking ‘Execute workflow’": {
"main": [
[
{
"node": "Code",
"type": "main",
"index": 0
}
]
]
},
"Code": {
"main": [
[
{
"node": "Loop Over Items",
"type": "main",
"index": 0
}
]
]
},
"Loop Over Items": {
"main": [
[],
[
{
"node": "RSS Read",
"type": "main",
"index": 0
}
]
]
},
"RSS Read": {
"main": [
[
{
"node": "Loop Over Items",
"type": "main",
"index": 0
}
]
]
}
},
"pinData": {},
"meta": {
"instanceId": "cb484ba7b742928a2048bf8829668bed5b5ad9787579adea888f05980292a4a7"
}
}
