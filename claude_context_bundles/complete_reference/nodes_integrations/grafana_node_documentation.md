# Grafana node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.grafana/

---

# Grafana node

Use the Grafana node to automate work in Grafana, and integrate Grafana with other applications. n8n has built-in support for a wide range of Grafana features, including creating, updating, deleting, and getting dashboards, teams, and users.

Credentials

Refer to [Grafana credentials](../../credentials/grafana/) for guidance on setting up authentication.

This node can be used as an AI tool

This node can be used to enhance the capabilities of an AI agent. When used in this way, many parameters can be set automatically, or with information directed by AI - find out more in the [AI tool parameters documentation](../../../../advanced-ai/examples/using-the-fromai-function/).

## Operations

- Dashboard
  - Create a dashboard
  - Delete a dashboard
  - Get a dashboard
  - Get all dashboards
  - Update a dashboard
- Team
  - Create a team
  - Delete a team
  - Get a team
  - Retrieve all teams
  - Update a team
- Team Member
  - Add a member to a team
  - Retrieve all team members
  - Remove a member from a team
- User
  - Delete a user from the current organization
  - Retrieve all users in the current organization
  - Update a user in the current organization

## Templates and examples

[Browse Grafana integration templates](https://n8n.io/integrations/grafana/), or [search all templates](https://n8n.io/workflows/)

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.
