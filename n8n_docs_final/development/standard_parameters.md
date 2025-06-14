# Standard parameters

**Source:** https://docs.n8n.io/integrations/creating-nodes/build/reference/node-base-files/standard-parameters/

---

# Standard parameters

These are the standard parameters for the [node base file](../). They're the same for all node types.

## `displayName`

*String* | *Required*

This is the name users see in the n8n GUI.

## `name`

*String* | *Required*

The internal name of the object. Used to reference it from other places in the node.

## `icon`

*String* or *Object* | *Required*

Specifies an icon for a particular node. n8n recommends uploading your own image file.

You can provide the icon file name as a string, or as an object to handle different icons for light and dark modes.
If the icon works in both light and dark modes, use a string that starts with `file:`, indicating the path to the icon file. For example:

| ``` 1 ``` | ``` icon: 'file:exampleNodeIcon.svg'  ``` |

To provide different icons for light and dark modes, use an object with `light` and `dark` properties. For example:

| ``` 1 2 3 4 ``` | ``` icon: {    light: 'file:exampleNodeIcon.svg',    dark: 'file:exampleNodeIcon.dark.svg'  }  ``` |

n8n recommends using an SVG for your node icon, but you can also use PNG. If using PNG, the icon resolution should be 60x60px. Node icons should have a square or near-square aspect ratio.

Don't reference Font Awesome

If you want to use a Font Awesome icon in your node, download and embed the image.

## `group`

*Array of strings* | *Required*

Tells n8n how the node behaves when the workflow runs. Options are:

- `trigger`: node waits for a trigger.
- `schedule`: node waits for a timer to expire.
- `input`, `output`, `transform`: these currently have no effect.
- An empty array, `[]`. Use this as the default option if you don't need `trigger` or `schedule`.

## `description`

*String* | *Required*

A short description of the node. n8n uses this in the GUI.

## `defaults`

*Object* | *Required*

Contains essential brand and name settings.

The object can include:

- `name`: String. Used as the node name on the canvas if the `displayName` is too long.
- `color`: String. Hex color code. Provide the brand color of the integration for use in n8n.

## `forceInputNodeExecution`

*Boolean* | *Optional*

When building a multi-input node, you can choose to force all preceding nodes on all branches to execute before the node runs. The default is `false` (requiring only one input branch to run).

## `inputs`

*Array of strings* | *Required*

Names the input connectors. Controls the number of connectors the node has on the input side. If you need only one connector, use `input: ['main']`.

## `outputs`

*Array of strings* | *Required*

Names the output connectors. Controls the number of connectors the node has on the output side. If you need only one connector, use `output: ['main']`.

## `requiredInputs`

*Integer* or *Array* | *Optional*

Used for multi-input nodes. Specify inputs by number that must have data (their branches must run) before the node can execute.

## `credentials`

*Array of objects* | *Required*

This parameter tells n8n the credential options. Each object defines an authentication type.

The object must include:

- `name`: the credential name. Must match the `name` property in the credential file. For example, `name: 'asanaApi'` in [`Asana.node.ts`](https://github.com/n8n-io/n8n/blob/master/packages/nodes-base/nodes/Asana/Asana.node.ts) links to `name = 'asanaApi'` in [`AsanaApi.credential.ts`](https://github.com/n8n-io/n8n/blob/master/packages/nodes-base/credentials/AsanaApi.credentials.ts).
- `required`: Boolean. Specify whether authentication is required to use this node.

## `requestDefaults`

*Object* | *Required*

Set up the basic information for the API calls the node makes.

This object must include:

- `baseURL`: The API base URL.

You can also add:

- `headers`: an object describing the API call headers, such as content type.
- `url`: string. Appended to the `baseURL`. You can usually leave this out. It's more common to provide this in the `operations`.

## `properties`

*Array of objects* | *Required*

This contains the resource and operations objects that define node behaviors, as well as objects to set up mandatory and optional fields that can receive user input.

### Resource objects

A resource object includes the following parameters:

- `displayName`: String. This should always be `Resource`.
- `name`: String. This should always be `resource`.
- `type`: String. Tells n8n which UI element to use, and what input type to expect. For example, `options` results in n8n adding a dropdown that allows users to choose one option. Refer to [Node UI elements](../../ui-elements/) for more information.
- `noDataExpression`: Boolean. Prevents using an expression for the parameter. Must always be `true` for `resource`.

### Operations objects

The operations object defines the available operations on a resource.

- `displayName`: String. This should always be `Options`.
- `name`: String. This should always be `option`.
- `type`: String. Tells n8n which UI element to use, and what input type to expect. For example, `dateTime` results in n8n adding a date picker. Refer to [Node UI elements](../../ui-elements/) for more information.
- `noDataExpression`: Boolean. Prevents using an expression for the parameter. Must always be `true` for `operation`.
- `options`: Array of objects. Each objects describes an operation's behavior, such as its routing, the REST verb it uses, and so on. An `options` object includes:
  - `name`. String.
  - `value`. String.
  - `action`: String. This parameter combines the resource and operation. You should always include it, as n8n will use it in future versions. For example, given a resource called `"Card"` and an operation `"Get all"`, your action is `"Get all cards"`.
  - `description`: String.
  - `routing`: Object containing request details.

### Additional fields objects

These objects define optional parameters. n8n displays them under **Additional Fields** in the GUI. Users can choose which parameters to set.

The objects must include:

| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 ``` | ``` displayName: 'Additional Fields', name: 'additionalFields', // The UI element type type: '' placeholder: 'Add Field', default: {}, displayOptions: {   // Set which resources and operations this field is available for   show: {     resource: [       // Resource names     ],     operation: [       // Operation names     ]   }, }  ``` |

For more information about UI element types, refer to [UI elements](../../ui-elements/).
