# Disable the public REST API

**Source:** https://docs.n8n.io/hosting/securing/disable-public-api/

---

# Disable the public REST API

The [n8n public REST API](../../../api/) allows you to programmatically perform many of the same tasks as you can in the n8n GUI.

If you don't plan on using this API, n8n recommends disabling it to improve the security of your n8n installation.

To disable the [public REST API](../../../api/), set the `N8N_PUBLIC_API_DISABLED` environment variable to `true`, for example:

| ``` 1 ``` | ``` export N8N_PUBLIC_API_DISABLED=true  ``` |

## Disable the API playground

To disable the [API playground](../../../api/using-api-playground/), set the `N8N_PUBLIC_API_SWAGGERUI_DISABLED` environment variable to `true`, for example:

| ``` 1 ``` | ``` export N8N_PUBLIC_API_SWAGGERUI_DISABLED=true  ``` |

## Related resources

Refer to [Deployment environment variables](../../configuration/environment-variables/deployment/) for more information on these environment variables.

Refer to [Configuration](../../configuration/configuration-methods/) for more information on setting environment variables.
