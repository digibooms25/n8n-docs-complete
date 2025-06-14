# Item linking for node creators

**Source:** https://docs.n8n.io/data/data-mapping/data-item-linking/item-linking-node-building/

---

# Item linking for node creators

Programmatic-style nodes only

This guidance applies to programmatic-style nodes. If you're using declarative style, n8n handles paired items for you automatically.

Use n8n's item linking to access data from items that precede the current item. n8n needs to know which input item a given output item comes from. If this information is missing, expressions in other nodes may break. As a node developer, you must ensure any items returned by your node support this.

This applies to programmatic nodes (including trigger nodes). You don't need to consider item linking when building a declarative-style node. Refer to [Choose your node building approach](../../../../integrations/creating-nodes/plan/choose-node-method/) for more information on node styles.

Start by reading [Item linking concepts](../item-linking-concepts/), which provides a conceptual overview of item linking, and details of the scenarios where n8n can handle the linking automatically.

If you need to handle item linking manually, do this by setting `pairedItem` on each item your node returns:

| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 ``` | ``` // Use the pairedItem information of the incoming item newItem = { 	"json": { . . . }, 	"pairedItem": { 		"item": item.pairedItem, 		// Optional: choose the input to use 		// Set this if your node combines multiple inputs 		"input": 0 };  // Or set the index manually newItem = { 		"json": { . . . } 		"pairedItem": { 			"item": i, 			// Optional: choose the input to use 			// Set this if your node combines multiple inputs 			"input": 0 		}, };  ``` |
