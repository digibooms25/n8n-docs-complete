# Beeminder credentials

**Source:** https://docs.n8n.io/integrations/builtin/credentials/beeminder/

---

# Beeminder credentials

You can use these credentials to authenticate the following node:

- [Beeminder](../../app-nodes/n8n-nodes-base.beeminder/)

## Prerequisites

Create a [Beeminder](https://www.beeminder.com/) account.

## Supported authentication methods

- API user token

## Related resources

Refer to [Beeminder's API documentation](https://api.beeminder.com/#beeminder-api-reference) for more information about the service.

## Using API user token

To configure this credential, you'll need:

- A **User** name: Should match the user who the Auth Token is generated for.
- A personal **Auth Token** for that user. Generate this using either method below:
  - In the GUI: From the [Apps & API](https://help.beeminder.com/article/110-apps-and-api#API-token) option within **Account Settings**
  - In the API: From hitting the [`auth_token` API endpoint](https://api.beeminder.com/#auth)
