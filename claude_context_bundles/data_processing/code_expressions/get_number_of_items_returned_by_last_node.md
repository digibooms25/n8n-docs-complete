# Get number of items returned by last node

**Source:** https://docs.n8n.io/code/cookbook/code-node/number-items-last-node/

---

# Get number of items returned by the previous node

To get the number of items returned by the previous node:

JavaScriptPython

| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 ``` | ``` if (Object.keys(items[0].json).length === 0) { return [ 	{ 		json: { 			results: 0, 		} 	} ] } return [ 	{ 		json: { 			results: items.length, 		} 	} ];  ``` |

The output will be similar to the following.

| ``` 1 2 3 4 5 ``` | ``` [ 	{ 		"results": 8 	} ]  ``` |

| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 ``` | ``` if len(items[0].json) == 0: 	return [ 		{ 			"json": { 				"results": 0, 			} 		} 	] else: 	return [ 		{ 			"json": { 				"results": items.length, 			} 		} 	]  ``` |

The output will be similar to the following.

| ``` 1 2 3 4 5 ``` | ``` [ 	{ 		"results": 8 	} ]  ``` |
