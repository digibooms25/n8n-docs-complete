# No Title

**Source:** https://docs.n8n.io/_workflows//courses/level-one/chapter-2.json

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
"id": "5738d1d8-ae7d-4e04-bca4-885c59e1d9e8",
"name": "When clicking ‘Execute workflow’"
},
{
"parameters": {
"resource": "all",
"limit": 10,
"additionalFields": {
"keyword": "automation"
}
},
"type": "n8n-nodes-base.hackerNews",
"typeVersion": 1,
"position": [
220,
],
"id": "65e9d0a6-5261-4c7d-8d85-6ff49de04dee",
"name": "Hacker News",
"notesInFlow": true,
"notes": "Get the 10 latest articles."
}
],
"connections": {
"When clicking ‘Execute workflow’": {
"main": [
[
{
"node": "Hacker News",
"type": "main",
"index": 0
}
]
]
}
},
"pinData": {},
"meta": {
"instanceId": "24789c4d5aa56ca018d140332e7a43fd37dd7af0409453314fff12dc1aeebfa8"
}
}
