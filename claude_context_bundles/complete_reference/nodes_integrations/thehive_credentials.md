# TheHive credentials

**Source:** https://docs.n8n.io/integrations/builtin/credentials/thehive/

---

# TheHive credentials

You can use these credentials to authenticate the following nodes:

- [TheHive](../../app-nodes/n8n-nodes-base.thehive/)

TheHive and TheHive 5

n8n provides two nodes for TheHive. Use these credentials with TheHive node for TheHive 3 or TheHive 4. If you're using TheHive5 node, use [TheHive 5 credentials](../thehive5/).

## Prerequisites

Install [TheHive](https://github.com/TheHive-Project/TheHiveDocs/blob/master/installation/install-guide.md) on your server.

## Supported authentication methods

- API key

## Related resources

Refer to [TheHive 3's API documentation](https://docs.thehive-project.org/thehive/legacy/thehive3/api/) and [TheHive 4's API documentation](https://docs.thehive-project.org/thehive/) for more information about the services.

## Using API key

To configure this credential, you'll need:

- An **API Key**: Create an API key from **Organization > Create API Key**. Refer to [API Authentication](https://docs.thehive-project.org/thehive/legacy/thehive3/api/authentication/) for more information.
- Your **URL**: The URL of your TheHive server.
- An **API Version**: Choose between:
  - **TheHive 3 (api v0)**
  - **TheHive 4 (api v1)**
  - For TheHive 5, use [TheHive 5 credentials](../thehive5/) instead.
- **Ignore SSL Issues**: When turned on, n8n will connect even if SSL certificate validation fails.
