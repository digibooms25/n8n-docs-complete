# Use case

**Source:** https://docs.n8n.io/courses/level-two/chapter-5/chapter-5.0/

---

# Automating a business workflow

Remember [our friend Nathan](../../../level-one/chapter-3/)?

**Nathan 🙋:** Hello, it's me again. My manager was so impressed with my first workflow automation solution that she entrusted me with more responsibility.
**You 👩‍🔧:** More work and responsibility. Congratulations, I guess. What do you need to do now?
**Nathan 🙋:** I got access to all our sales data and I'm now responsible for creating two reports: one for regional sales and one for orders prices. They're based on data from different sources and come in different formats.
**You 👩‍🔧:** Sounds like a lot of manual work, but the kind that can be automated. Let's do it!

## Workflow design

Now that we know what Nathan wants to automate, let's list the steps he needs to take to achieve this:

1. Get and combine data from all necessary sources.
2. Sort the data and format the dates.
3. Write binary files.
4. Send notifications using email and Discord.

n8n provides [core nodes](../../../../integrations/builtin/node-types/#core-nodes) for all these steps. This use case is somewhat complex. We should build it from three separate workflows:

1. A workflow that merges the company data with external information.
2. A workflow that generates the reports.
3. A workflow that monitors errors in the second workflow.

## Workflow prerequisites

To build the workflows, you will need the following:

- An [Airtable](https://airtable.com/) account and [credentials](../../../../integrations/builtin/credentials/airtable/).
- A [Google](https://www.google.com/account/about/) account and [credentials](../../../../integrations/builtin/credentials/google/) to access Gmail.
- A [Discord](https://discord.com/) account and webhook URL (you receive this using email when you sign up for this course).

Next, you will build these three workflows with step-by-step instructions.
