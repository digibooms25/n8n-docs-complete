# Convenience methods

**Source:** https://docs.n8n.io/code/builtin/convenience/

---

# Convenience methods

n8n provides these methods to make it easier to perform common tasks in [expressions](../../../glossary/#expression-n8n).

Python support

You can use Python in the Code node. It isn't available in expressions.

JavaScriptPython

| Method | Description | Available in Code node? |
| `$evaluateExpression(expression: string, itemIndex?: number)` | Evaluates a string as an expression. If you don't provide `itemIndex`, n8n uses the data from item 0 in the Code node. | ✅ |
| `$ifEmpty(value, defaultValue)` | The `$ifEmpty()` function takes two parameters, tests the first to check if it's empty, then returns either the parameter (if not empty) or the second parameter (if the first is empty). The first parameter is empty if it's:  - `undefined` - `null` - An empty string `''` - An array where `value.length` returns `false` - An object where `Object.keys(value).length` returns `false` | ✅ |
| `$if()` | The `$if()` function takes three parameters: a condition, the value to return if true, and the value to return if false. | ❌ |
| `$max()` | Returns the highest of the provided numbers. | ❌ |
| `$min()` | Returns the lowest of the provided numbers. | ❌ |

| Method | Description |
| `_evaluateExpression(expression: string, itemIndex?: number)` | Evaluates a string as an expression. If you don't provide `itemIndex`, n8n uses the data from item 0 in the Code node. |
| `_ifEmpty(value, defaultValue)` | The `_ifEmpty()` function takes two parameters, tests the first to check if it's empty, then returns either the parameter (if not empty) or the second parameter (if the first is empty). The first parameter is empty if it's:  - `undefined` - `null` - An empty string `''` - An array where `value.length` returns `false` - An object where `Object.keys(value).length` returns `false` |
