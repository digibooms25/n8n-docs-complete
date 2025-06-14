# Google Ads node documentation

**Source:** https://docs.n8n.io/integrations/builtin/app-nodes/n8n-nodes-base.googleads/

---

# Google Ads node

Use the Google Ads node to automate work in Google Ads, and integrate Google Ads with other applications. n8n has built-in support for a wide range of Google Ads features, including getting campaigns.

Credentials

Refer to [Google Ads credentials](../../credentials/google/) for guidance on setting up authentication.

## Operations

- Campaign
- Get all campaigns
- Get a campaign

## Templates and examples

**AI marketing report (Google Analytics & Ads, Meta Ads), sent via email/Telegram**

by Friedemann Schuetz

[View template details](https://n8n.io/workflows/2783-ai-marketing-report-google-analytics-and-ads-meta-ads-sent-via-emailtelegram/)

**Generating New Keywords and their Search Volumes using the Google Ads API**

by Imperol

[View template details](https://n8n.io/workflows/2695-generating-new-keywords-and-their-search-volumes-using-the-google-ads-api/)

**Get Meta Ads insights and save them into Google Sheets**

by Solomon

[View template details](https://n8n.io/workflows/2714-get-meta-ads-insights-and-save-them-into-google-sheets/)

[Browse Google Ads integration templates](https://n8n.io/integrations/google-ads/), or [search all templates](https://n8n.io/workflows/)

## Related resources

Refer to [Google Ads' documentation](https://developers.google.com/google-ads/api/docs/start) for more information about the service.

## What to do if your operation isn't supported

If this node doesn't support the operation you want to do, you can use the [HTTP Request node](../../core-nodes/n8n-nodes-base.httprequest/) to call the service's API.

You can use the credential you created for this service in the HTTP Request node:

1. In the HTTP Request node, select **Authentication** > **Predefined Credential Type**.
2. Select the service you want to connect to.
3. Select your credential.

Refer to [Custom API operations](../../../custom-operations/) for more information.
