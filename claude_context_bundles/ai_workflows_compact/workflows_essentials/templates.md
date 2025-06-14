# Templates

**Source:** https://docs.n8n.io/workflows/templates/

---

# Workflow templates

When creating a new workflow, you can choose whether to start with an empty workflow, or use an existing [template](../../glossary/#template-n8n).

Templates provide:

- Help getting started: n8n might already have a template that does what you need.
- Examples of what you can build
- Best practices for creating your own workflows

## Access templates

Select ![View templates icon](../../_images/common-icons/templates.png) **Templates** to view the templates library.

If you use n8n's template library, this takes you to browse [Workflows on the n8n website](https://n8n.io/workflows/). If you use a custom library provided by your organization, you'll be able to search and browse the templates within the app.

## Add your workflow to the n8n library

You can submit your workflows to n8n's template library.

n8n is working on a creator program, and developing a marketplace of templates. This is an ongoing project, and details are likely to change.

Refer to [n8n Creator hub](https://www.notion.so/n8n/n8n-Creator-hub-7bd2cbe0fce0449198ecb23ff4a2f76f) for information on how to submit templates and become a creator.

## Self-hosted n8n: Disable templates

In your environment variables, set `N8N_TEMPLATES_ENABLED` to false.

## Self-hosted n8n: Use your own library

In your environment variables, set `N8N_TEMPLATES_HOST` to the base URL of your API.

### Endpoints

Your API must provide the same endpoints and data structure as n8n's.

The endpoints are:

| Method | Path |
| GET | /templates/workflows/`<id>` |
| GET | /templates/search |
| GET | /templates/collections/`<id>` |
| GET | /templates/collections |
| GET | /templates/categories |
| GET | /health |

### Query parameters

The `/templates/search` endpoint accepts the following query parameters:

| Parameter | Type | Description |
| `page` | integer | The page of results to return |
| `rows` | integer | The maximum number of results to return per page |
| `category` | comma-separated list of strings (categories) | The categories to search within |
| `search` | string | The search query |

The `/templates/collections` endpoint accepts the following query parameters:

| Parameter | Type | Description |
| `category` | comma-separated list of strings (categories) | The categories to search within |
| `search` | string | The search query |

### Data schema

You can explore the data structure of the items in the response object returned by endpoints here:

Show `workflow` item data schema

| Workflow item data schema | |
| ```   1   2   3   4   5   6   7   8   9  10  11  12  13  14  15  16  17  18  19  20  21  22  23  24  25  26  27  28  29  30  31  32  33  34  35  36  37  38  39  40  41  42  43  44  45  46  47  48  49  50  51  52  53  54  55  56  57  58  59  60  61  62  63  64  65  66  67  68  69  70  71  72  73  74  75  76  77  78  79  80  81  82  83  84  85  86  87  88  89  90  91  92  93  94  95  96  97  98  99 100 101 102 103 104 105 106 107 108 109 110 111 112 113 114 115 116 117 118 119 120 121 122 123 124 125 126 127 128 129 130 131 132 133 134 135 136 137 138 139 140 141 142 143 144 145 146 147 148 149 150 151 152 153 154 155 156 157 158 159 160 161 162 163 164 165 166 167 168 169 170 171 172 173 174 175 176 177 178 179 180 181 182 183 184 185 186 187 188 189 190 191 192 193 194 195 196 197 198 199 200 201 202 203 204 205 206 207 ``` | ``` {   "$schema": "http://json-schema.org/draft-07/schema#",   "title": "Generated schema for Root",   "type": "object",   "properties": {     "id": {       "type": "number"     },     "name": {       "type": "string"     },     "totalViews": {       "type": "number"     },     "price": {},     "purchaseUrl": {},     "recentViews": {       "type": "number"     },     "createdAt": {       "type": "string"     },     "user": {       "type": "object",       "properties": {         "username": {           "type": "string"         },         "verified": {           "type": "boolean"         }       },       "required": [         "username",         "verified"       ]     },     "nodes": {       "type": "array",       "items": {         "type": "object",         "properties": {           "id": {             "type": "number"           },           "icon": {             "type": "string"           },           "name": {             "type": "string"           },           "codex": {             "type": "object",             "properties": {               "data": {                 "type": "object",                 "properties": {                   "details": {                     "type": "string"                   },                   "resources": {                     "type": "object",                     "properties": {                       "generic": {                         "type": "array",                         "items": {                           "type": "object",                           "properties": {                             "url": {                               "type": "string"                             },                             "icon": {                               "type": "string"                             },                             "label": {                               "type": "string"                             }                           },                           "required": [                             "url",                             "label"                           ]                         }                       },                       "primaryDocumentation": {                         "type": "array",                         "items": {                           "type": "object",                           "properties": {                             "url": {                               "type": "string"                             }                           },                           "required": [                             "url"                           ]                         }                       }                     },                     "required": [                       "primaryDocumentation"                     ]                   },                   "categories": {                     "type": "array",                     "items": {                       "type": "string"                     }                   },                   "nodeVersion": {                     "type": "string"                   },                   "codexVersion": {                     "type": "string"                   }                 },                 "required": [                   "categories"                 ]               }             }           },           "group": {             "type": "string"           },           "defaults": {             "type": "object",             "properties": {               "name": {                 "type": "string"               },               "color": {                 "type": "string"               }             },             "required": [               "name"             ]           },           "iconData": {             "type": "object",             "properties": {               "icon": {                 "type": "string"               },               "type": {                 "type": "string"               },               "fileBuffer": {                 "type": "string"               }             },             "required": [               "type"             ]           },           "displayName": {             "type": "string"           },           "typeVersion": {             "type": "number"           },           "nodeCategories": {             "type": "array",             "items": {               "type": "object",               "properties": {                 "id": {                   "type": "number"                 },                 "name": {                   "type": "string"                 }               },               "required": [                 "id",                 "name"               ]             }           }         },         "required": [           "id",           "icon",           "name",           "codex",           "group",           "defaults",           "iconData",           "displayName",           "typeVersion"         ]       }     }   },   "required": [     "id",     "name",     "totalViews",     "price",     "purchaseUrl",     "recentViews",     "createdAt",     "user",     "nodes"   ] }  ``` |

Show `category` item data schema

| Category item data schema | |
| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 ``` | ``` {   "$schema": "http://json-schema.org/draft-07/schema#",   "type": "object",   "properties": {     "id": {       "type": "number"     },     "name": {       "type": "string"     }   },   "required": [     "id",     "name"   ] }  ``` |

Show `collection` item data schema

| Collection item data schema | |
| ```  1  2  3  4  5  6  7  8  9 10 11 12 13 14 15 16 17 18 19 20 21 22 23 24 25 26 27 28 29 30 31 32 33 34 35 36 37 38 39 40 41 42 43 44 45 46 ``` | ``` {   "$schema": "http://json-schema.org/draft-07/schema#",   "type": "object",   "properties": {     "id": {       "type": "number"     },     "rank": {       "type": "number"     },     "name": {       "type": "string"     },     "totalViews": {},     "createdAt": {       "type": "string"     },     "workflows": {       "type": "array",       "items": {         "type": "object",         "properties": {           "id": {             "type": "number"           }         },         "required": [           "id"         ]       }     },     "nodes": {       "type": "array",       "items": {}     }   },   "required": [     "id",     "rank",     "name",     "totalViews",     "createdAt",     "workflows",     "nodes"   ] }  ``` |

You can also interactively explore n8n's API endpoints:

<https://api.n8n.io/templates/categories>
<https://api.n8n.io/templates/collections>
<https://api.n8n.io/templates/search>
<https://api.n8n.io/health>

You can [contact us](mailto:help@n8n.io) for more support.
