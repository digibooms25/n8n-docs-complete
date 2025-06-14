# Tutorial: Build a declarative-style node

**Source:** https://docs.n8n.io/integrations/creating-nodes/build/declarative-style-node/

---

# Build a declarative-style node

This tutorial walks through building a declarative-style node. Before you begin, make sure this is the node style you need. Refer to [Choose your node building approach](../../plan/choose-node-method/) for more information.

## Prerequisites

You need the following installed on your development machine:

- [git](https://git-scm.com/downloads)
- Node.js and npm. Minimum version Node 18.17.0. You can find instructions on how to install both using nvm (Node Version Manager) for Linux, Mac, and WSL [here](https://github.com/nvm-sh/nvm). For Windows users, refer to Microsoft's guide to [Install NodeJS on Windows](https://docs.microsoft.com/en-us/windows/dev-environment/javascript/nodejs-on-windows).

You need some understanding of:

- JavaScript/TypeScript
- REST APIs
- git

## Build your node

Existing node

n8n has a built-in NASA node. To avoid clashing with the existing node, you'll give your version a different name.

### Step 1: Set up the project

n8n provides a starter repository for node development. Using the starter ensures you have all necessary dependencies. It also provides a linter.

Clone the repository and navigate into the directory:

1. [Generate a new repository](https://github.com/n8n-io/n8n-nodes-starter/generate) from the template repository.
2. Clone your new repository:

   | ``` 1 2 ``` | ``` git clone https://github.com/<your-organization>/<your-repo-name>.git n8n-nodes-nasa-pics cd n8n-nodes-nasa-pics  ``` |

The starter contains example nodes and credentials. Delete the following directories and files:

- `nodes/ExampleNode`
- `nodes/HTTPBin`
- `credentials/ExampleCredentials.credentials.ts`
- `credentials/HttpBinApi.credentials.ts`

Now create the following directories and files:

`nodes/NasaPics`
`nodes/NasaPics/NasaPics.node.json`
`nodes/NasaPics/NasaPics.node.ts`
`credentials/NasaPicsApi.credentials.ts`

These are the key files required for any node. Refer to [Node file structure](../reference/node-file-structure/) for more information on required files and recommended organization.

Now install the project dependencies:

| ``` 1 ``` | ``` npm i  ``` |

### Step 2: Add an icon

Save the NASA SVG logo from [here](https://upload.wikimedia.org/wikipedia/commons/e/e5/NASA_logo.svg) as `nasapics.svg` in `nodes/NasaPics/`.

n8n recommends using an SVG for your node icon, but you can also use PNG. If using PNG, the icon resolution should be 60x60px. Node icons should have a square or near-square aspect ratio.

Don't reference Font Awesome

If you want to use a Font Awesome icon in your node, download and embed the image.

### Step 3: Create the node

Every node must have a base file. Refer to [Node base file](../reference/node-base-files/) for detailed information about base file parameters.

In this example, the file is `NasaPics.node.ts`. To keep this tutorial short, you'll place all the node functionality in this one file. When building more complex nodes, you should consider splitting out your functionality into modules. Refer to [Node file structure](../reference/node-file-structure/) for more information.

#### Step 3.1: Imports

Start by adding the import statements:

| ``` 1 ``` | ``` import { INodeType, INodeTypeDescription } from 'n8n-workflow';  ``` |

#### Step 3.2: Create the main class

The node must export an interface that implements INodeType. This interface must include a `description` interface, which in turn contains the `properties` array.

Class names and file names

Make sure the class name and the file name match. For example, given a class `NasaPics`, the filename must be `NasaPics.node.ts`.

| ``` 1 2 3 4 5 6 7 8 ``` | ``` export class NasaPics implements INodeType { 	description: INodeTypeDescription = { 		// Basic node details will go here 		properties: [ 		// Resources and operations will go here 		] 	}; }  ``` |

#### Step 3.3: Add node details

All nodes need some basic parameters, such as their display name, icon, and the basic information for making a request using the node. Add the following to the `description`:

| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 ``` | ``` displayName: 'NASA Pics', name: 'NasaPics', icon: 'file:nasapics.svg', group: ['transform'], version: 1, subtitle: '={{$parameter["operation"] + ": " + $parameter["resource"]}}', description: 'Get data from NASAs API', defaults: { 	name: 'NASA Pics', }, inputs: ['main'], outputs: ['main'], credentials: [ 	{ 		name: 'NasaPicsApi', 		required: true, 	}, ], requestDefaults: { 	baseURL: 'https://api.nasa.gov', 	headers: { 		Accept: 'application/json', 		'Content-Type': 'application/json', 	}, },  ``` |

n8n uses some of the properties set in `description` to render the node in the Editor UI. These properties are `displayName`, `icon`, `description`, and `subtitle`.

#### Step 3.4: Add resources

The resource object defines the API resource that the node uses. In this tutorial, you're creating a node to access two of NASA's API endpoints: `planetary/apod` and `mars-photos`. This means you need to define two resource options in `NasaPics.node.ts`. Update the `properties` array with the resource object:

| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 ``` | ``` properties: [ 	{ 		displayName: 'Resource', 		name: 'resource', 		type: 'options', 		noDataExpression: true, 		options: [ 			{ 				name: 'Astronomy Picture of the Day', 				value: 'astronomyPictureOfTheDay', 			}, 			{ 				name: 'Mars Rover Photos', 				value: 'marsRoverPhotos', 			}, 		], 		default: 'astronomyPictureOfTheDay', 	}, 	// Operations will go here  ]  ``` |

`type` controls which UI element n8n displays for the resource, and tells n8n what type of data to expect from the user. `options` results in n8n adding a dropdown that allows users to choose one option. Refer to [Node UI elements](../reference/ui-elements/) for more information.

#### Step 3.5: Add operations

The operations object defines the available operations on a resource.

In a declarative-style node, the operations object includes `routing` (within the `options` array). This sets up the details of the API call.

Add the following to the `properties` array, after the `resource` object:

| ```   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17  18  19  20  21  22  23  24  25  26  27  28  29  30  31  32  33  34  35  36  37  38  39  40  41  42  43  44  45  46  47  48  49  50  51  52  53  54  55  56  57  58  59  60  61  62  63  64  65  66  67  68  69  70  71  72  73  74  75  76  77  78  79  80  81  82  83  84  85  86  87  88  89  90  91  92  93  94  95  96  97  98  99 100 101 102 103 104 105 ``` | ``` { 	displayName: 'Operation', 	name: 'operation', 	type: 'options', 	noDataExpression: true, 	displayOptions: { 		show: { 			resource: [ 				'astronomyPictureOfTheDay', 			], 		}, 	}, 	options: [ 		{ 			name: 'Get', 			value: 'get', 			action: 'Get the APOD', 			description: 'Get the Astronomy Picture of the day', 			routing: { 				request: { 					method: 'GET', 					url: '/planetary/apod', 				}, 			}, 		}, 	], 	default: 'get', }, { 	displayName: 'Operation', 	name: 'operation', 	type: 'options', 	noDataExpression: true, 	displayOptions: { 		show: { 			resource: [ 				'marsRoverPhotos', 			], 		}, 	}, 	options: [ 		{ 			name: 'Get', 			value: 'get', 			action: 'Get Mars Rover photos', 			description: 'Get photos from the Mars Rover', 			routing: { 				request: { 					method: 'GET', 				}, 			}, 		}, 	], 	default: 'get', }, { 	displayName: 'Rover name', 	description: 'Choose which Mars Rover to get a photo from', 	required: true, 	name: 'roverName', 	type: 'options', 	options: [ 		{name: 'Curiosity', value: 'curiosity'}, 		{name: 'Opportunity', value: 'opportunity'}, 		{name: 'Perseverance', value: 'perseverance'}, 		{name: 'Spirit', value: 'spirit'}, 	], 	routing: { 		request: { 			url: '=/mars-photos/api/v1/rovers/{{$value}}/photos', 		}, 	}, 	default: 'curiosity', 	displayOptions: { 		show: { 			resource: [ 				'marsRoverPhotos', 			], 		}, 	}, }, { 	displayName: 'Date', 	description: 'Earth date', 	required: true, 	name: 'marsRoverDate', 	type: 'dateTime', 	default:'', 	displayOptions: { 		show: { 			resource: [ 				'marsRoverPhotos', 			], 		}, 	}, 	routing: { 		request: { 			// You've already set up the URL. qs appends the value of the field as a query string 			qs: { 				earth_date: '={{ new Date($value).toISOString().substr(0,10) }}', 			}, 		}, 	}, }, // Optional/additional fields will go here  ``` |

This code creates two operations: one to get today's APOD image, and another to send a get request for photos from one of the Mars Rovers. The object named `roverName` requires the user to choose which Rover they want photos from. The `routing` object in the Mars Rover operation references this to create the URL for the API call.

#### Step 3.6: Optional fields

Most APIs, including the NASA API that you're using in this example, have optional fields you can use to refine your query.

To avoid overwhelming users, n8n displays these under **Additional Fields** in the UI.

For this tutorial, you'll add one additional field, to allow users to pick a date to use with the APOD endpoint. Add the following to the properties array:

| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 ``` | ``` { 	displayName: 'Additional Fields', 	name: 'additionalFields', 	type: 'collection', 	default: {}, 	placeholder: 'Add Field', 	displayOptions: { 		show: { 			resource: [ 				'astronomyPictureOfTheDay', 			], 			operation: [ 				'get', 			], 		}, 	}, 	options: [ 		{ 			displayName: 'Date', 			name: 'apodDate', 			type: 'dateTime', 			default: '', 			routing: { 				request: { 					// You've already set up the URL. qs appends the value of the field as a query string 					qs: { 						date: '={{ new Date($value).toISOString().substr(0,10) }}', 					}, 				}, 			}, 		}, 	],									 }  ``` |

### Step 4: Set up authentication

The NASA API requires users to authenticate with an API key.

Add the following to `nasaPicsApi.credentials.ts`:

| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 ``` | ``` import { 	IAuthenticateGeneric, 	ICredentialType, 	INodeProperties, } from 'n8n-workflow';  export class NasaPicsApi implements ICredentialType { 	name = 'NasaPicsApi'; 	displayName = 'NASA Pics API'; 	// Uses the link to this tutorial as an example 	// Replace with your own docs links when building your own nodes 	documentationUrl = 'https://docs.n8n.io/integrations/creating-nodes/build/declarative-style-node/'; 	properties: INodeProperties[] = [ 		{ 			displayName: 'API Key', 			name: 'apiKey', 			type: 'string', 			default: '', 		}, 	]; 	authenticate = { 		type: 'generic', 		properties: { 			qs: { 				'api_key': '={{$credentials.apiKey}}' 			} 		}, 	} as IAuthenticateGeneric; }  ``` |

For more information about credentials files and options, refer to [Credentials file](../reference/credentials-files/).

### Step 5: Add node metadata

Metadata about your node goes in the JSON file at the root of your node. n8n refers to this as the codex file. In this example, the file is `NasaPics.node.json`.

Add the following code to the JSON file:

| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 ``` | ``` { 	"node": "n8n-nodes-base.NasaPics", 	"nodeVersion": "1.0", 	"codexVersion": "1.0", 	"categories": [ 		"Miscellaneous" 	], 	"resources": { 		"credentialDocumentation": [ 			{ 				"url": "" 			} 		], 		"primaryDocumentation": [ 			{ 				"url": "" 			} 		] 	} }  ``` |

For more information on these parameters, refer to [Node codex files](../reference/node-codex-files/).

### Step 6: Update the npm package details

Your npm package details are in the `package.json` at the root of the project. It's essential to include the `n8n` object with links to the credentials and base node file. Update this file to include the following information:

| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 ``` | ``` { 	// All node names must start with "n8n-nodes-" 	"name": "n8n-nodes-nasapics", 	"version": "0.1.0", 	"description": "n8n node to call NASA's APOD and Mars Rover Photo services.", 	"keywords": [ 		// This keyword is required for community nodes 		"n8n-community-node-package" 	], 	"license": "MIT", 	"homepage": "https://n8n.io", 	"author": { 		"name": "Test", 		"email": "test@example.com" 	}, 	"repository": { 		"type": "git", 		// Change the git remote to your own repository 		// Add the new URL here 		"url": "git+<your-repo-url>" 	}, 	"main": "index.js", 	"scripts": { 		// don't change 	}, 	"files": [ 		"dist" 	], 	// Link the credentials and node 	"n8n": { 		"n8nNodesApiVersion": 1, 		"credentials": [ 			"dist/credentials/NasaPicsApi.credentials.js" 		], 		"nodes": [ 			"dist/nodes/NasaPics/NasaPics.node.js" 		] 	}, 	"devDependencies": { 		// don't change 	}, 	"peerDependencies": { 		// don't change 	} }  ``` |

You need to update the `package.json` to include your own information, such as your name and repository URL. For more information on npm `package.json` files, refer to [npm's package.json documentation](https://docs.npmjs.com/cli/v8/configuring-npm/package-json).

## Test your node

You can test your node as you build it by running it in a local n8n instance.

1. Install n8n using npm:

   | ``` 1 ``` | ``` npm install n8n -g  ``` |
2. When you are ready to test your node, publish it locally:

   | ``` 1 2 3 ``` | ``` # In your node directory npm run build npm link  ``` |
3. Install the node into your local n8n instance:

   | ``` 1 2 3 ``` | ``` # In the nodes directory within your n8n installation # node-package-name is the name from the package.json npm link <node-package-name>  ``` |

   Check your directory

   Make sure you run `npm link <node-name>` in the nodes directory within your n8n installation. This can be:

   - `~/.n8n/custom/`
   - `~/.n8n/<your-custom-name>`: if your n8n installation set a different name using `N8N_CUSTOM_EXTENSIONS`.
4. Start n8n:

   | ``` 1 ``` | ``` n8n start  ``` |
5. Open n8n in your browser. You should see your nodes when you search for them in the nodes panel.

   Node names

   Make sure you search using the node name, not the package name. For example, if your npm package name is `n8n-nodes-weather-nodes`, and the package contains nodes named `rain`, `sun`, `snow`, you should search for `rain`, not `weather-nodes`.

### Troubleshooting

- There's no `custom` directory in `~/.n8n` local installation.

You have to create `custom` directory manually and run `npm init`

| ``` 1 2 3 4 ``` | ``` # In ~/.n8n directory run mkdir custom  cd custom  npm init  ``` |

## Next steps

- [Deploy your node](../../deploy/).
- View an example of a declarative node: n8n's [Brevo node](https://github.com/n8n-io/n8n/tree/master/packages/nodes-base/nodes/Brevo). Note that the main node is declarative, while the trigger node is in programmatic style.
- Learn about [node versioning](../reference/node-versioning/).
