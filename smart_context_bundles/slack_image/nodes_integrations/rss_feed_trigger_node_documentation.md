# RSS Feed Trigger node documentation

**Source:** https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.rssfeedreadtrigger/

---

# RSS Feed Trigger node

The RSS Feed Trigger node allows you to start an n8n workflow when a new RSS feed item has been published.

## Node parameters

- **Poll Times**: Select a poll **Mode** to set how often to trigger the poll. Your **Mode** selection will add or remove relevant fields. Refer to the sections below to configure the parameters for each mode type.
- **Feed URL**: Enter the URL of the RSS feed to poll.

### Every Hour mode

Enter the **Minute** of the hour to trigger the poll, from `0` to `59`.

### Every Day mode

- Enter the **Hour** of the day to trigger the poll in 24-hour format, from `0` to `23`.
- Enter the **Minute** of the hour to trigger the poll, from `0` to `59`.

### Every Week mode

- Enter the **Hour** of the day to trigger the poll in 24-hour format, from `0` to `23`.
- Enter the **Minute** of the hour to trigger the poll, from `0` to `59`.
- Select the **Weekday** to trigger the poll.

### Every Month mode

- Enter the **Hour** of the day to trigger the poll in 24-hour format, from `0` to `23`.
- Enter the **Minute** of the hour to trigger the poll, from `0` to `59`.
- Enter the **Day of the Month** to trigger the poll, from `0` to `31`.

### Every X mode

- Enter the **Value** of measurement for how often to trigger the poll in either minutes or hours.
- Select the **Unit** for the value. Supported units are **Minutes** and **Hours**.

### Custom mode

Enter a custom **Cron Expression** to trigger the poll. Use these values and ranges:

- Seconds: `0` - `59`
- Minutes: `0` - `59`
- Hours: `0` - `23`
- Day of Month: `1` - `31`
- Months: `0` - `11` (Jan - Dec)
- Day of Week: `0` - `6` (Sun - Sat)

To generate a Cron expression, you can use [crontab guru](https://crontab.guru). Paste the Cron expression that you generated using crontab guru in the **Cron Expression** field in n8n.

#### Examples

If you want to trigger your workflow every day at 04:08:30, enter the following in the **Cron Expression** field.

| ``` 1 ``` | ``` 30 8 4 * * *  ``` |

If you want to trigger your workflow every day at 04:08, enter the following in the **Cron Expression** field.

| ``` 1 ``` | ``` 8 4 * * *  ``` |

#### Why there are six asterisks in the Cron expression

The sixth asterisk in the Cron expression represents seconds. Setting this is optional. The node will execute even if you don't set the value for seconds.

| * | * | * | * | * | * |
| second | minute | hour | day of month | month | day of week |

## Templates and examples

**Create an RSS feed based on a website's content**

by Tom

[View template details](https://n8n.io/workflows/1418-create-an-rss-feed-based-on-a-websites-content/)

**Scrape and summarize posts of a news site without RSS feed using AI and save them to a NocoDB**

by Askan

[View template details](https://n8n.io/workflows/2180-scrape-and-summarize-posts-of-a-news-site-without-rss-feed-using-ai-and-save-them-to-a-nocodb/)

**Read RSS feed from two different sources**

by Deborah

[View template details](https://n8n.io/workflows/687-read-rss-feed-from-two-different-sources/)

[Browse RSS Feed Trigger integration templates](https://n8n.io/integrations/rss-feed-trigger/), or [search all templates](https://n8n.io/workflows/)

## Related resources

n8n provides an app node for RSS Feeds. You can find the node docs [here](../n8n-nodes-base.rssfeedread/).
