# No Title

**Source:** https://docs.n8n.io/_workflows/integrations/builtin/core-nodes/n8n-nodes-base.form/mutually-exclusive-branching.json

---

{
"name": "Form with mutually exclusive branching",
"nodes": [
{
"parameters": {
"formTitle": "Form with mutually exclusive branching",
"formDescription": "This form contains branches, but only one branch will ever be executed.",
"formFields": {
"values": [
{
"fieldLabel": "Would you recommend this site?",
"fieldType": "dropdown",
"fieldOptions": {
"values": [
{
"option": "Yes"
},
{
"option": "No"
}
]
},
"requiredField": true
}
]
},
"options": {}
},
"type": "n8n-nodes-base.formTrigger",
"typeVersion": 2.2,
"position": [
0,
],
"id": "1adce353-28c9-48b8-8326-c1f41d9311fd",
"name": "On form submission",
"webhookId": "d869b846-111d-4f53-96e4-2c4a533d9ed6"
},
{
"parameters": {
"rules": {
"values": [
{
"conditions": {
"options": {
"caseSensitive": true,
"leftValue": "",
"typeValidation": "strict",
"version": 2
},
"conditions": [
{
"leftValue": "={{ $json['Would you recommend this site?'] }}",
"rightValue": "Yes",
"operator": {
"type": "string",
"operation": "equals"
}
}
],
"combinator": "and"
},
"renameOutput": true,
"outputKey": "Yes"
},
{
"conditions": {
"options": {
"caseSensitive": true,
"leftValue": "",
"typeValidation": "strict",
"version": 2
},
"conditions": [
{
"id": "1dd9b1f5-6f48-4182-ae04-f47c37e3fa98",
"leftValue": "={{ $json['Would you recommend this site?'] }}",
"rightValue": "No",
"operator": {
"type": "string",
"operation": "equals",
"name": "filter.operator.equals"
}
}
],
"combinator": "and"
},
"renameOutput": true,
"outputKey": "No"
}
]
},
"options": {}
},
"type": "n8n-nodes-base.switch",
"typeVersion": 3.2,
"position": [
220,
],
"id": "c0d3e3f1-76c5-4bac-8382-c3d70a57ee8a",
"name": "Switch"
},
{
"parameters": {
"formFields": {
"values": [
{
"fieldLabel": "What can we do to improve?",
"fieldType": "textarea"
}
]
},
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
440,
],
"id": "615cf27a-658c-43be-aff9-c5fda8a04c51",
"name": "If not recommended",
"webhookId": "3579ba77-7ba2-4a97-8a29-a228aac297d5"
},
{
"parameters": {
"operation": "completion",
"completionTitle": "Thank you for your review!",
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
660,
-200
],
"id": "13423b3f-0380-429d-92bf-460cc8b409a3",
"name": "Thanks for the review",
"webhookId": "bce3f77b-3005-4989-bd61-b9c5ff19e59e"
},
{
"parameters": {
"operation": "completion",
"completionTitle": "Thank you for your feedback",
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
660,
],
"id": "0848a392-41f2-47e8-be17-124fef3d9a63",
"name": "Thanks for the feedback",
"webhookId": "8b1a34e2-aa24-4c12-841c-79f6491cb779"
},
{
"parameters": {
"content": "## Form with mutually exclusive branching\nThis form contains a branch where only one of the two paths will execute, depending on your selections.",
"width": 380
},
"type": "n8n-nodes-base.stickyNote",
"position": [
-160,
-260
],
"typeVersion": 1,
"id": "57c5e1cd-7dda-4bfb-8bfa-8c9f91110249",
"name": "Sticky Note"
},
{
"parameters": {
"content": "This Switch node determines which branch will execute.\n\nThe switch uses data from a dropdown field with single selection enforced, so only one path will execute.",
"color": 5
},
"type": "n8n-nodes-base.stickyNote",
"position": [
440,
],
"typeVersion": 1,
"id": "9bde0398-7021-4ec6-b950-d836979c973b",
"name": "Sticky Note1"
},
{
"parameters": {
"formFields": {
"values": [
{
"fieldLabel": "Leave your review below",
"fieldType": "textarea"
}
]
},
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
440,
-200
],
"id": "9956a49e-964d-4269-910f-28ad8393548e",
"name": "If recommended",
"webhookId": "f8298b40-1f61-465b-b228-30a659075f30"
}
],
"pinData": {},
"connections": {
"On form submission": {
"main": [
[
{
"node": "Switch",
"type": "main",
"index": 0
}
]
]
},
"Switch": {
"main": [
[
{
"node": "If recommended",
"type": "main",
"index": 0
}
],
[
{
"node": "If not recommended",
"type": "main",
"index": 0
}
]
]
},
"If not recommended": {
"main": [
[
{
"node": "Thanks for the feedback",
"type": "main",
"index": 0
}
]
]
},
"If recommended": {
"main": [
[
{
"node": "Thanks for the review",
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
"versionId": "6797e22c-1b2b-421a-b16d-869f636d0790",
"meta": {
"instanceId": "1f94e052868811125a74dc63385a38f60e7a14ab6e00497af83e8b68412ec251"
},
"id": "DCotkGqkv0VfT6QT",
"tags": []
}
