# Manual Trigger node documentation

**Source:** https://docs.n8n.io/integrations/builtin/core-nodes/n8n-nodes-base.manualworkflowtrigger/

---

# Manual Trigger node

Use this node if you want to start a workflow by selecting **Test Workflow** and don't want any option for the workflow to run automatically.

Workflows always need a trigger, or start point. Most workflows start with a trigger node firing in response to an external event or the [Schedule Trigger](../n8n-nodes-base.scheduletrigger/) firing on a set schedule.

The Manual Trigger node serves as the workflow trigger for workflows that don't have an automatic trigger.

Use this trigger:

- To test your workflow before you add an automatic trigger of some kind.
- When you don't want the workflow to run automatically.

## Common issues

Here are some common errors and issues with the Manual Trigger node and steps to resolve or troubleshoot them.

### Only one 'Manual Trigger' node is allowed in a workflow

This error displays if you try to add a Manual Trigger node to a workflow which already includes a Manual Trigger node.

Remove your existing Manual Trigger or edit your workflow to connect that trigger to a different node.
