# Trello node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.trello/

---

# Trello node

Use the Trello node to automate work in Trello, and integrate Trello with other applications. n8n has built-in support for a wide range of Trello features, including creating and updating cards, and adding and removing members.

Credentials

Refer to [Trello credentials](../../credentials/trello/) for guidance on setting up authentication.

This node can be used as an AI tool

This node can be used to enhance the capabilities of an AI agent. When used in this way, many parameters can be set automatically, or with information directed by AI - find out more in the [AI tool parameters documentation](../../../../advanced-ai/examples/using-the-fromai-function/).

## Operations

- Attachment
  - Create a new attachment for a card
  - Delete an attachment
  - Get the data of an attachment
  - Returns all attachments for the card
- Board
  - Create a new board
  - Delete a board
  - Get the data of a board
  - Update a board
- Board Member
  - Add
  - Get All
  - Invite
  - Remove
- Card
  - Create a new card
  - Delete a card
  - Get the data of a card
  - Update a card
- Card Comment
  - Create a comment on a card
  - Delete a comment from a card
  - Update a comment on a card
- Checklist
  - Create a checklist item
  - Create a new checklist
  - Delete a checklist
  - Delete a checklist item
  - Get the data of a checklist
  - Returns all checklists for the card
  - Get a specific checklist on a card
  - Get the completed checklist items on a card
  - Update an item in a checklist on a card
- Label
  - Add a label to a card.
  - Create a new label
  - Delete a label
  - Get the data of a label
  - Returns all labels for the board
  - Remove a label from a card.
  - Update a label.
- List
  - Archive/Unarchive a list
  - Create a new list
  - Get the data of a list
  - Get all the lists
  - Get all the cards in a list
  - Update a list

## Templates and examples

**RSS Feed News Processing and Distribution Workflow**

by PollupAI

[View template details](https://n8n.io/workflows/2785-rss-feed-news-processing-and-distribution-workflow/)

**Process Shopify new orders with Zoho CRM and Harvest**

by Lorena

[View template details](https://n8n.io/workflows/1206-process-shopify-new-orders-with-zoho-crm-and-harvest/)

**Sync Google Calendar tasks to Trello every day**

by Angel Menendez

[View template details](https://n8n.io/workflows/1118-sync-google-calendar-tasks-to-trello-every-day/)

[Browse Trello integration templates](https://n8n.io/integrations/trello/), or [search all templates](https://n8n.io/workflows/)

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.

## Find the List ID

1. Open the Trello board that contains the list.
2. If the list doesn't have any cards, add a card to the list.
3. Open the card, add `.json` at the end of the URL, and press enter.
4. In the JSON file, you will see a field called `idList`.
5. Copy the contents of the `idList`field and paste it in the ***List ID** field in n8n.
