# No Title

**Source:** https://docs.n8n.io/_workflows/integrations/builtin/core-nodes/n8n-nodes-base.form/multiple-branch-execution.json

---

{
"name": "Form that can execute multiple branches",
"nodes": [
{
"parameters": {
"formTitle": "Form that may execute multiple branches",
"formDescription": "This form contains multiple branches. Depending on the user's responses, more than one branch may execute sequentially.",
"formFields": {
"values": [
{
"fieldLabel": "What are your favorite film genres",
"fieldType": "dropdown",
"fieldOptions": {
"values": [
{
"option": "Documentary"
},
{
"option": "Action"
},
{
"option": "Romance"
},
{
"option": "Comedy"
},
{
"option": "Drama"
}
]
},
"multiselect": true,
"requiredField": true
}
]
},
"options": {}
},
"type": "n8n-nodes-base.formTrigger",
"typeVersion": 2.2,
"position": [
-300,
],
"id": "ad3f0e0a-a1e9-4504-8711-508bd29bd745",
"name": "On form submission",
"webhookId": "b3e1c86f-ae45-421e-9045-f19873b7a73e"
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
"id": "e3d995dd-d555-4e7a-b744-a3434ed602ad",
"leftValue": "={{ $json['What are your favorite film genres'] }}",
"rightValue": "Documentary",
"operator": {
"type": "array",
"operation": "contains",
"rightType": "any"
}
}
],
"combinator": "and"
},
"renameOutput": true,
"outputKey": "Documentary"
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
"id": "ae94981b-1273-4830-ac2a-991bb25f41d8",
"leftValue": "={{ $json['What are your favorite film genres'] }}",
"rightValue": "Action",
"operator": {
"type": "array",
"operation": "contains",
"rightType": "any"
}
}
],
"combinator": "and"
},
"renameOutput": true,
"outputKey": "Action"
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
"id": "b9545089-4054-484d-9e6c-98f4872e7e9e",
"leftValue": "={{ $json['What are your favorite film genres'] }}",
"rightValue": "Romance",
"operator": {
"type": "array",
"operation": "contains",
"rightType": "any"
}
}
],
"combinator": "and"
},
"renameOutput": true,
"outputKey": "Romance"
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
"id": "71ae5a41-0927-40e3-a583-e569bcebfd1f",
"leftValue": "={{ $json['What are your favorite film genres'] }}",
"rightValue": "Comedy",
"operator": {
"type": "array",
"operation": "contains",
"rightType": "any"
}
}
],
"combinator": "and"
},
"renameOutput": true,
"outputKey": "Comedy"
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
"id": "5bfe5981-203a-457a-bfaa-36846d7b79a8",
"leftValue": "={{ $json['What are your favorite film genres'] }}",
"rightValue": "Drama",
"operator": {
"type": "array",
"operation": "contains",
"rightType": "any"
}
}
],
"combinator": "and"
},
"renameOutput": true,
"outputKey": "Drama"
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
"id": "adb1bfc5-08fd-4653-abe0-6f12aedda16a",
"leftValue": "={{ $json['What are your favorite film genres'] }}",
"rightValue": 1,
"operator": {
"type": "array",
"operation": "lengthGt",
"rightType": "number"
}
}
],
"combinator": "and"
},
"renameOutput": true,
"outputKey": "Final page"
}
]
},
"options": {
"allMatchingOutputs": true
}
},
"type": "n8n-nodes-base.switch",
"typeVersion": 3.2,
"position": [
100,
],
"id": "df96da7b-c7dc-43c6-8941-973842603e0c",
"name": "Switch"
},
{
"parameters": {
"content": "## Form that may execute multiple branches\nThis form contains branching where more than one path may execute, depending on the user's selections.",
"width": 380
},
"type": "n8n-nodes-base.stickyNote",
"position": [
-160,
-260
],
"typeVersion": 1,
"id": "c51af5ad-8f6c-4f2a-8974-65c4abc4fcbf",
"name": "Sticky Note"
},
{
"parameters": {
"content": "This Switch node determines which branches will execute.\n\nMultiple conditions may be true, resulting in more than one branch being executed. When this happens, n8n executes the first branch completely before returning to execute the next branch.",
"height": 220,
"width": 260,
"color": 5
},
"type": "n8n-nodes-base.stickyNote",
"position": [
20,
],
"typeVersion": 1,
"id": "eab3ff17-5030-4556-a0c7-2571345e8cdf",
"name": "Sticky Note1"
},
{
"parameters": {
"formFields": {
"values": [
{
"fieldLabel": "What is your favorite documentary?"
}
]
},
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
700,
-500
],
"id": "dc55c82f-7d4f-4368-8ab5-69a673e92027",
"name": "Documentary questions",
"webhookId": "0c72f06e-4cc0-41eb-931c-7bf82bb1927e"
},
{
"parameters": {
"formFields": {
"values": [
{
"fieldLabel": "What is your favorite action film?"
}
]
},
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
700,
-280
],
"id": "3f76b5df-561b-4159-9e14-33a43d8c45a8",
"name": "Action questions",
"webhookId": "bea04786-25cc-477e-aaf1-ab68159cbe28"
},
{
"parameters": {
"operation": "completion",
"completionTitle": "Thank you for answering our documentary questions!",
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
920,
-500
],
"id": "16660e2e-a047-45d2-ba54-12d573633ece",
"name": "Documentary thanks",
"webhookId": "0238f2c2-8984-4adc-aade-308bb458c16e"
},
{
"parameters": {
"operation": "completion",
"completionTitle": "Thank you for answering our action film questions!",
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
920,
-280
],
"id": "1853276a-3ba6-4315-b772-fbeb0c68a477",
"name": "Action thanks",
"webhookId": "2e47b563-bd17-466c-86b7-9237be55d226"
},
{
"parameters": {
"formFields": {
"values": [
{
"fieldLabel": "What is your favorite romance film?"
}
]
},
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
700,
],
"id": "cd7bc8d0-a143-4733-be84-320c88ef241b",
"name": "Romance questions",
"webhookId": "3f77a665-fc03-46ba-a58f-6d9bd7099028"
},
{
"parameters": {
"operation": "completion",
"completionTitle": "Thank you for answering our romance film questions!",
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
920,
],
"id": "42d7c8b5-f66f-4b34-821c-0df91bbaa9ea",
"name": "Romance thanks",
"webhookId": "eee896c5-d116-4586-972d-3fe02073ed11"
},
{
"parameters": {
"formFields": {
"values": [
{
"fieldLabel": "What is your favorite comedy film?"
}
]
},
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
700,
],
"id": "b9422abf-1ad5-44e4-941d-692f72bc2fef",
"name": "Comedy questions",
"webhookId": "97b56894-28fb-47d1-b729-754e43f1ac09"
},
{
"parameters": {
"operation": "completion",
"completionTitle": "Thank you for answering our comedy film questions!",
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
920,
],
"id": "1db70bda-0752-41b7-a930-b90f6e64b3e7",
"name": "Comedy thanks",
"webhookId": "b021494a-5a35-4ade-b7c0-ca43a309268d"
},
{
"parameters": {
"formFields": {
"values": [
{
"fieldLabel": "What is your favorite drama film?"
}
]
},
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
700,
],
"id": "2bef931a-12d2-4873-ad19-9bdb0b5fe78f",
"name": "Drama questions",
"webhookId": "8d801d97-1103-42ee-a0c1-c1f1153727d9"
},
{
"parameters": {
"operation": "completion",
"completionTitle": "Thank you for answering our drama film questions!",
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
920,
],
"id": "1fd7fa2f-d1be-430a-bb98-ded89ad8fca0",
"name": "Drama thanks",
"webhookId": "46a782bc-21b2-4fcd-9c52-82a7bb20ec2c"
},
{
"parameters": {
"operation": "completion",
"completionTitle": "Thank you for answering our film questions!",
"options": {}
},
"type": "n8n-nodes-base.form",
"typeVersion": 1,
"position": [
700,
],
"id": "7b0aeed0-0e13-4fcb-a3e9-c5ff4d6a77ca",
"name": "Multi-selection thank you",
"webhookId": "67fcd1f3-e5a6-4bf6-b17e-37b2a87f4c3d"
},
{
"parameters": {
"content": "n8n Form nodes using the **Form Ending** page type are only executed if they are the last node in the execution path.\n\nThese endings specific to a genre are only executed if this is the only valid branch.",
"height": 1400,
"width": 280,
"color": 5
},
"type": "n8n-nodes-base.stickyNote",
"position": [
840,
-740
],
"typeVersion": 1,
"id": "7bda913a-d75c-4b20-8be6-a767c008a8f6",
"name": "Sticky Note2"
},
{
"parameters": {
"content": "\n\n\n\n\n\n\n\n\n\n\n\n\n\n\n\nThe switch includes this **Form Ending** node whenever more than one branch is executed.\n\nBecause this is the [final branch](https://docs.n8n.io/flow-logic/execution-order/) that will be executed, this is the final display whenever multiple branches are executed.",
"height": 400,
"width": 300,
"color": 5
},
"type": "n8n-nodes-base.stickyNote",
"position": [
740,
],
"typeVersion": 1,
"id": "9c3f93a5-5248-4ba1-99b5-9df6d21416c2",
"name": "Sticky Note3"
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
"node": "Documentary questions",
"type": "main",
"index": 0
}
],
[
{
"node": "Action questions",
"type": "main",
"index": 0
}
],
[
{
"node": "Romance questions",
"type": "main",
"index": 0
}
],
[
{
"node": "Comedy questions",
"type": "main",
"index": 0
}
],
[
{
"node": "Drama questions",
"type": "main",
"index": 0
}
],
[
{
"node": "Multi-selection thank you",
"type": "main",
"index": 0
}
]
]
},
"Documentary questions": {
"main": [
[
{
"node": "Documentary thanks",
"type": "main",
"index": 0
}
]
]
},
"Action questions": {
"main": [
[
{
"node": "Action thanks",
"type": "main",
"index": 0
}
]
]
},
"Romance questions": {
"main": [
[
{
"node": "Romance thanks",
"type": "main",
"index": 0
}
]
]
},
"Comedy questions": {
"main": [
[
{
"node": "Comedy thanks",
"type": "main",
"index": 0
}
]
]
},
"Drama questions": {
"main": [
[
{
"node": "Drama thanks",
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
"versionId": "b1d38757-38ea-4ee8-a352-990185b17e31",
"meta": {
"instanceId": "1f94e052868811125a74dc63385a38f60e7a14ab6e00497af83e8b68412ec251"
},
"id": "kl3goXzWrfrWHpYv",
"tags": []
}
