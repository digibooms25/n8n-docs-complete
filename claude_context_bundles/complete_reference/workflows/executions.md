# Executions

**Source:** https://docs.n8n.io/workflows/executions/

---

# Executions

An execution is a single run of a workflow.

## Execution modes

There are two execution modes:

- Manual: run workflows manually when testing. Select **Test Workflow** to start a manual execution. You can do manual executions of active workflows, but n8n recommends keeping your workflow set to **Inactive** while developing and testing.
- Production: a production workflow is one that runs automatically. To enable this, set the workflow to **Active**.

## Execution lists

n8n provides two execution lists:

- [Workflow-level executions](single-workflow-executions/): this execution list shows the executions for a single workflow.
- [All executions](all-executions/): this list shows all executions for all your workflows.

n8n supports [adding custom data to executions](custom-executions-data/).
