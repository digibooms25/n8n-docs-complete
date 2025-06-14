# Current node input

**Source:** https://docs.n8n.io/code/builtin/current-node-input/

---

# Current node input

Methods for working with the input of the current node. Some methods and variables aren't available in the Code node.

Python support

You can use Python in the Code node. It isn't available in expressions.

JavaScriptPython

| Method | Description | Available in Code node? |
| `$binary` | Shorthand for `$input.item.binary`. Incoming binary data from a node | ❌ |
| `$input.item` | The input item of the current node that's being processed. Refer to [Item linking](../../../data/data-mapping/data-item-linking/) for more information on paired items and item linking. | ✅ |
| `$input.all()` | All input items in current node. | ✅ |
| `$input.first()` | First input item in current node. | ✅ |
| `$input.last()` | Last input item in current node. | ✅ |
| `$input.params` | Object containing the query settings of the previous node. This includes data such as the operation it ran, result limits, and so on. | ✅ |
| `$json` | Shorthand for `$input.item.json`. Incoming JSON data from a node. Refer to [Data structure](../../../data/data-structure/) for information on item structure. | ✅ (when running once for each item) |
| `$input.context.noItemsLeft` | Boolean. Only available when working with the Loop Over Items node. Provides information about what's happening in the node. Use this to determine whether the node is still processing items. | ✅ |

| Method | Description |
| `_input.item` | The input item of the current node that's being processed. Refer to [Item linking](../../../data/data-mapping/data-item-linking/) for more information on paired items and item linking. |
| `_input.all()` | All input items in current node. |
| `_input.first()` | First input item in current node. |
| `_input.last()` | Last input item in current node. |
| `_input.params` | Object containing the query settings of the previous node. This includes data such as the operation it ran, result limits, and so on. |
| `_json` | Shorthand for `_input.item.json`. Incoming JSON data from a node. Refer to [Data structure](../../../data/data-structure/) for information on item structure. Available when you set **Mode** to **Run Once for Each Item**. |
| `_input.context.noItemsLeft` | Boolean. Only available when working with the Loop Over Items node. Provides information about what's happening in the node. Use this to determine whether the node is still processing items. |
