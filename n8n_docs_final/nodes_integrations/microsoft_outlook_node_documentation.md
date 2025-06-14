# Microsoft Outlook node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.microsoftoutlook/

---

# Microsoft Outlook node

Use the Microsoft Outlook node to automate work in Microsoft Outlook, and integrate Microsoft Outlook with other applications. n8n has built-in support for a wide range of Microsoft Outlook features, including creating, updating, deleting, and getting folders, messages, and drafts.

Credentials

Refer to [Microsoft credentials](../../credentials/microsoft/) for guidance on setting up authentication.

This node can be used as an AI tool

This node can be used to enhance the capabilities of an AI agent. When used in this way, many parameters can be set automatically, or with information directed by AI - find out more in the [AI tool parameters documentation](../../../../advanced-ai/examples/using-the-fromai-function/).

## Operations

- Calendar
  - Create
  - Delete
  - Get
  - Get Many
  - Update
- Contact
  - Create
  - Delete
  - Get
  - Get Many
  - Update
- Draft
  - Create
  - Delete
  - Get
  - Send
  - Update
- Event
  - Create
  - Delete
  - Get
  - Get Many
  - Update
- Folder
  - Create
  - Delete
  - Get
  - Get Many
  - Update
- Folder Message
  - Get Many
- Message
  - Delete
  - Get
  - Get Many
  - Move
  - Reply
  - Send
  - Send and Wait for Response
  - Update
- Message Attachment
  - Add
  - Download
  - Get
  - Get Many

## Waiting for a response

By choosing the **Send and Wait for a Response** operation, you can send a message and pause the workflow execution until a person confirms the action or provides more information.

### Response Type

You can choose between the following types of waiting and approval actions:

- **Approval**: Users can approve or disapprove from within the message.
- **Free Text**: Users can submit a response with a form.
- **Custom Form**: Users can submit a response with a custom form.

You can customize the waiting and response behavior depending on which response type you choose. You can configure these options in any of the above response types:

- **Limit Wait Time**: Whether the workflow will automatically resume execution after a specified time limit. This can be an interval or a specific wall time.
- **Append n8n Attribution**: Whether to mention in the message that it was sent automatically with n8n (turned on) or not (turned off).

### Approval response customization

When using the Approval response type, you can choose whether to present only an approval button or both approval *and* disapproval buttons.

You can also customize the button labels for the buttons you include.

### Free Text response customization

When using the Free Text response type, you can customize the message button label, the form title and description, and the response button label.

### Custom Form response customization

When using the Custom Form response type, you build a form using the fields and options you want.

You can customize each form element with the settings outlined in the [n8n Form trigger's form elements](../../core-nodes/n8n-nodes-base.formtrigger/#form-elements). To add more fields, select the **Add Form Element** button.

You'll also be able to customize the message button label, the form title and description, and the response button label.

## Templates and examples

**Create a Branded AI-Powered Website Chatbot**

by Wayne Simpson

[View template details](https://n8n.io/workflows/2786-create-a-branded-ai-powered-website-chatbot/)

**Auto Categorise Outlook Emails with AI**

by Wayne Simpson

[View template details](https://n8n.io/workflows/2454-auto-categorise-outlook-emails-with-ai/)

**Phishing Analysis - URLScan.io and VirusTotal**

by n8n Team

[View template details](https://n8n.io/workflows/1992-phishing-analysis-urlscanio-and-virustotal/)

[Browse Microsoft Outlook integration templates](https://n8n.io/integrations/microsoft-outlook/), or [search all templates](https://n8n.io/workflows/)

## Related resources

Refer to [Outlook's API documentation](https://learn.microsoft.com/en-us/outlook/rest/get-started) for more information about the service.

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.
