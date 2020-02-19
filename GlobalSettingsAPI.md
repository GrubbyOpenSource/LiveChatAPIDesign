# API

## Summary

- [Visitor](#Visitor)
- [Custom Agent Away Status](#Custom-Agent-Away-Status)
- [Public Canned Message](#Public-Canned-Message)
- [Public Canned Message Category](#Public-Canned-Message-Category)
- [Private Canned Message](#Private-Canned-Message)
- [Private Canned Message Category](#Private-Canned-Message-Category)
- [Agent SSO](#Agent-SSO)
- [Visitor SSO](#Visitor-SSO)
- [Shift](#Shift)

## Visitor

  You need `Manage Settings` permission to manage visitor.

- `GET /api/v3/livechat/visitors` -get a list of visitor
- `GET /api/v3/livechat/visitors/chatting`  -get a list of chatting visitor
- `GET /api/v3/livechat/visitors/{id}`  -get a visitor
- `PUT /api/v3/livechat/visitors/{id}`  -update a visitor's custom variable

### Related Object Json Format

#### Visitor Object

  Visitor Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  |`id` | Guid  | | yes | N/A | | Id of the current item.  |
  | `name` | string  | N/A | yes |  | Name of the visitor. |
  | `email` | string  | N/A | N/A |  | Email of the visitor. |
  | `numberOfVisits` | integer  | N/A | N/A | 0 | The total number of web pages the visitor viewed on your website. |
  | `numberOfChats` | integer  | N/A | N/A | 0 | The total times of chats a visitor has made on your website from the first time to present. |
  | `firstVisitTime` | datetime  | N/A | N/A |  | The time the visitor first visited a web page pasted with Comm100 Live Chat code. |

### Visitor Endpoints

#### Get all visitors of a site

  `GET /api/v3/livechat/visitors`

##### Response

the response is: [Visitor](#Visitor-Object) Object

#### Get all chatting visitors of a site

  `GET /api/v3/livechat/visitors/chatting`

##### Response

the response is: [Visitor](#Visitor-Object) Object

#### Get a visitors by id

  `GET /api/v3/livechat/visitors/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the visitor |

##### Response

the response is: [Visitor](#Visitor-Object) Object

#### Update a visitors

  `PUT /api/v3/livechat/visitors/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the visitor |

Request Body

  The request body contains data with the [Visitor](#Visitor-Object) structure

##### Response

the response is: [Visitor](#Visitor-Object) Object

## Custom Agent Away Status

  You need `Manage Settings` permission to manage visitor.

- `GET /api/v3/livechat/customAwayStatus` - get a list of custom away status
- `GET /api/v3/livechat/customAwayStatus/{id}` - get a single custom away status
- `POST /api/v3/livechat/customAwayStatus` - create a new custom away status
- `PUT /api/v3/livechat/customAwayStatus/{id}` - update a custom away status
- `DELETE /api/v3/livechat/customAwayStatus/{id}` - remove a custom away status

### Related Object Json Format

#### Custom Away Status Object

  Custom Away Status Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  |`id` | Guid  | | yes | N/A | | Id of the current item.  |
  | `name` | string  | N/A | N/A |  | Name of the custom away status. |
  | `isSystem` | boolean  | N/A | N/A |  | Whether the custom away status is system or not. |
  | `order` | integer  | N/A | N/A | 0 | The order of the custom away status. |

### Custom Agent Away Status Endpoints

#### Get all Custom Agent Away Status of a site

  `GET /api/v3/livechat/customAwayStatus`

##### Response

the response is: [Custom Agent Away Status](#Custom-Agent-Away-Status-Object) Object

#### Get a Custom Agent Away Status by id

  `GET /api/v3/livechat/customAwayStatus/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the custom agent away status |

##### Response

the response is: [Custom Agent Away Status](#Custom-Agent-Away-Status-Object) Object

#### Create a new Custom Agent Away Status

  `POST /api/v3/livechat/customAwayStatus`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the custom agent away status |

Request Body

  The request body contains data with the [Custom Agent Away Status](#Custom-Agent-Away-Status-Object) structure

##### Response

the response is: [Custom Agent Away Status](#Custom-Agent-Away-Status-Object) Object

#### Update a Custom Agent Away Status

  `PUT /api/v3/livechat/customAwayStatus/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the custom agent away status |

Request Body

  The request body contains data with the [Custom Agent Away Status](#Custom-Agent-Away-Status-Object) structure

##### Response

the response is: [Custom Agent Away Status](#Custom-Agent-Away-Status-Object) Object

#### Delete a Custom Agent Away Status by id

  `DELETE /api/v3/livechat/customAwayStatus/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the custom agent away status |

##### Response

HTTP/1.1 204 No Content

## Public Canned Message

  You need `Manage Pulbic Canned Messages` permission to manage canned message.

- `GET /api/v3/livechat/publicCannedMessages` -get a list of canned Messages
- `GET /api/v3/livechat/publicCannedMessages/{id}`  -get a single canned Message
- `POST /api/v3/livechat/publicCannedMessages` -create a new canned Message
- `PUT /api/v3/livechat/publicCannedMessages/{id}`  -update a canned Message
- `DELETE /api/v3/livechat/publicCannedMessages/{id}`  -remove a canned Message

### Related Object Json Format

#### Public Canned Message Object

  Public Canned Message Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  |`id` | Guid  | | yes | N/A | | Id of the current item.  |
  | `name` | string  | N/A | N/A |  | Name of the canned message. |
  | `message` | string  | N/A | N/A |  | Whether the custom away status is system or not. |
  | `IfSetHTMLMessageForEmail` | boolean  | N/A | N/A |  |  |
  | `HTMLMessage` | string  | N/A | N/A |  |  |
  | `category` | [Public Canned Message Category](#Public-Canned-Message-Category-Object)  | N/A | N/A |  | Which category the current item belongs to. |
  | `createBy` | [Agent](#Agent-Object)  | N/A | N/A |  | Which agent create the current item. |
  | `shortcuts` | string  | N/A | N/A |  | Whether the custom away status is system or not. |
  | `channel` | string  | N/A | N/A | `default`,`email` | The default channel canned message works for all channel. Email channel canned message only works for Email channel. If a specific Channel is not added, use the Default Channel Canned Messages. |
  | `similarQuestion` | [Similar Question](#Similar-Question-Object)[]  | N/A | N/A | 0 | Available when Agent Assist is enabled. |

#### Similar Question Object

  Similar Question Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `question` | string  | N/A | N/A |  |  |

### Public Canned Message Endpoints

#### Get all Public Canned Message of a site

  `GET /api/v3/livechat/publicCannedMessages`

##### Response

the response is: [Public Canned Message](#Public-Canned-Message-Object) Object

#### Get a Public Canned Message by id

  `GET /api/v3/livechat/publicCannedMessages/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the public canned message |

##### Response

the response is: [Public Canned Message](#Public-Canned-Message-Object) Object

#### Create a new Public Canned Message

  `POST /api/v3/livechat/publicCannedMessages`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the public canned message |

Request Body

  The request body contains data with the [Public Canned Message](#Public-Canned-Message-Object) structure

##### Response

the response is: [Public Canned Message](#Public-Canned-Message-Object) Object

#### Update a Public Canned Message

  `PUT /api/v3/livechat/publicCannedMessages/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the public canned message |

Request Body

  The request body contains data with the [Public Canned Message](#Public-Canned-Message-Object) structure

##### Response

the response is: [Public Canned Message](#Public-Canned-Message-Object) Object

#### Delete a Public Canned Message by id

  `DELETE /api/v3/livechat/publicCannedMessages/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the public canned message |

##### Response

HTTP/1.1 204 No Content

## Public Canned Message Category

  You need `Manage Pulbic Canned Messages` permission to manage canned message category.

- `GET /api/v3/livechat/publicCannedMessageCategories` -get a list of canned Messages
- `GET /api/v3/livechat/publicCannedMessageCategories/{id}`  -get a single canned Message
- `POST /api/v3/livechat/publicCannedMessageCategories` -create a new canned Message
- `PUT /api/v3/livechat/publicCannedMessageCategories/{id}`  -update a canned Message
- `DELETE /api/v3/livechat/publicCannedMessageCategories/{id}`  -remove a canned Message

### Related Object Json Format

#### Public Canned Message Category Object

  Public Canned Message Category Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  |`id` | Guid  | | yes | N/A | | Id of the current item.  |
  | `name` | string  | N/A | N/A |  | Name of the canned message category. |
  | `parent` | string  | N/A | N/A |  | Parent of the canned message category. |
  | `createBy` | [Agent](#Agent-Object)  | N/A | N/A |  | Which agent create the current item. |

### Public Canned Message Endpoints

#### Get all Public Canned Message of a site

  `GET /api/v3/livechat/publicCannedMessageCategories`

##### Response

the response is: [Public Canned Message Category](#Public-Canned-Message-Category-Object) Object

#### Get a Public Canned Message by id

  `GET /api/v3/livechat/publicCannedMessageCategories/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the public canned message |

##### Response

the response is: [Public Canned Message Category](#Public-Canned-Message-Category-Object) Object

#### Create a new Public Canned Message

  `POST /api/v3/livechat/publicCannedMessageCategories`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the public canned message |

Request Body

  The request body contains data with the [Public Canned Message Category](#Public-Canned-Message-Category-Object) structure

##### Response

the response is: [Public Canned Message Category](#Public-Canned-Message-Category-Object) Object

#### Update a Public Canned Message

  `PUT /api/v3/livechat/publicCannedMessageCategories/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the public canned message |

Request Body

  The request body contains data with the [Public Canned Message Category](#Public-Canned-Message-Category-Object) structure

##### Response

the response is: [Public Canned Message Category](#Public-Canned-Message-Category-Object) Object

#### Delete a Public Canned Message by id

  `DELETE /api/v3/livechat/publicCannedMessageCategories/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the public canned message |

##### Response

HTTP/1.1 204 No Content

## Private Canned Message

- `GET /api/v3/livechat/privateCannedMessages` -get a list of canned Messages
- `GET /api/v3/livechat/privateCannedMessages/{id}`  -get a single canned Message
- `POST /api/v3/livechat/privateCannedMessages` -create a new canned Message
- `PUT /api/v3/livechat/privateCannedMessages/{id}`  -update a canned Message
- `DELETE /api/v3/livechat/privateCannedMessages/{id}`  -remove a canned Message

### Related Object Json Format

#### Private Canned Message Object

  Private Canned Message Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  |`id` | Guid  | | yes | N/A | | Id of the current item.  |
  | `name` | string  | N/A | N/A |  | Name of the canned message. |
  | `message` | string  | N/A | N/A |  | Whether the custom away status is system or not. |
  | `IfSetHTMLMessageForEmail` | boolean  | N/A | N/A |  |  |
  | `HTMLMessage` | string  | N/A | N/A |  |  |
  | `category` | [Private Canned Message Category](#Private-Canned-Message-Category-Object)  | N/A | N/A |  | Which category the current item belongs to. |
  | `createBy` | [Agent](#Agent-Object)  | N/A | N/A |  | Which agent create the current item. |
  | `shortcuts` | string  | N/A | N/A |  | Whether the custom away status is system or not. |
  | `channel` | string  | N/A | N/A | `default`,`email` | The default channel canned message works for all channel. Email channel canned message only works for Email channel. If a specific Channel is not added, use the Default Channel Canned Messages. |
  | `similarQuestion` | [Similar Question](#Similar-Question-Object)[]  | N/A | N/A | 0 | Available when Agent Assist is enabled. |

#### Similar Question Object

  Similar Question Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `question` | string  | N/A | N/A |  |  |

### Private Canned Message Endpoints

#### Get all Private Canned Message of a site

  `GET /api/v3/livechat/privateCannedMessages`

##### Response

the response is: [Private Canned Message](#Private-Canned-Message-Object) Object

#### Get a Private Canned Message by id

  `GET /api/v3/livechat/privateCannedMessages/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the Private canned message |

##### Response

the response is: [Private Canned Message](#Private-Canned-Message-Object) Object

#### Create a new Private Canned Message

  `POST /api/v3/livechat/privateCannedMessages`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the private canned message |

Request Body

  The request body contains data with the [Private Canned Message](#Private-Canned-Message-Object) structure

##### Response

the response is: [Private Canned Message](#Private-Canned-Message-Object) Object

#### Update a Private Canned Message

  `PUT /api/v3/livechat/privateCannedMessages/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the private canned message |

Request Body

  The request body contains data with the [Private Canned Message](#Private-Canned-Message-Object) structure

##### Response

the response is: [Private Canned Message](#Private-Canned-Message-Object) Object

#### Delete a Private Canned Message by id

  `DELETE /api/v3/livechat/privateCannedMessages/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the private canned message |

##### Response

HTTP/1.1 204 No Content

## Private Canned Message Category

  You need `Manage Pulbic Canned Messages` permission to manage canned message category.

- `GET /api/v3/livechat/publicCannedMessageCategories` -get a list of canned Messages
- `GET /api/v3/livechat/publicCannedMessageCategories/{id}`  -get a single canned Message
- `POST /api/v3/livechat/publicCannedMessageCategories` -create a new canned Message
- `PUT /api/v3/livechat/publicCannedMessageCategories/{id}`  -update a canned Message
- `DELETE /api/v3/livechat/publicCannedMessageCategories/{id}`  -remove a canned Message

### Related Object Json Format

#### Private Canned Message Category Object

  Private Canned Message Category Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  |`id` | Guid  | | yes | N/A | | Id of the current item.  |
  | `name` | string  | N/A | N/A |  | Name of the canned message category. |
  | `parent` | string  | N/A | N/A |  | Parent of the canned message category. |
  | `createBy` | [Agent](#Agent-Object)  | N/A | N/A |  | Which agent create the current item. |

### Private Canned Message Endpoints

#### Get all Private Canned Message of a site

  `GET /api/v3/livechat/publicCannedMessageCategories`

##### Response

the response is: [Private Canned Message Category](#Private-Canned-Message-Category-Object) Object

#### Get a Private Canned Message by id

  `GET /api/v3/livechat/publicCannedMessageCategories/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the private canned message |

##### Response

the response is: [Private Canned Message Category](#Private-Canned-Message-Category-Object) Object

#### Create a new Private Canned Message

  `POST /api/v3/livechat/publicCannedMessageCategories`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the private canned message |

Request Body

  The request body contains data with the [Private Canned Message Category](#Private-Canned-Message-Category-Object) structure

##### Response

the response is: [Private Canned Message Category](#Private-Canned-Message-Category-Object) Object

#### Update a Private Canned Message

  `PUT /api/v3/livechat/publicCannedMessageCategories/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the private canned message |

Request Body

  The request body contains data with the [Private Canned Message Category](#Private-Canned-Message-Category-Object) structure

##### Response

the response is: [Private Canned Message Category](#Private-Canned-Message-Category-Object) Object

#### Delete a Private Canned Message by id

  `DELETE /api/v3/livechat/publicCannedMessageCategories/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the Private canned message |

##### Response

HTTP/1.1 204 No Content

## Agent SSO

  You need `Manage Settings` permission to setting sso for a site.

- `GET /api/v3/livechat/agentSSO` -Get SSO settings of agent
- `PUT /api/v3/livechat/agentSSO`  -Update configuration of agent

### Related Object Json Format

#### Agent SSO Object

  Agent SSO Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `isEnabled` | boolean  | N/A | N/A |  |  |
  | `protocolType` | string  | N/A | N/A |  | enums: `SAML SSO`,`JWT SSO`. |
  | `SAMLSSOURL` | string  | N/A | N/A |  |Only available when Type is SAML SSO. |
  | `SAMLLogoutURL` | string  | N/A | N/A |  | Only available when Type is SAML SSO. |
  | `SAMLCertificateFileName` | string  | N/A | N/A |  | Only available when Type is SAML SSO. |
  | `JWTLoginURL` | string  | N/A | N/A |  | Only available when Type is JWT SSO. |
  | `JWTLogoutURL` | string  | N/A | N/A |  | Only available when Type is JWT SSO.  |
  | `JWTSecret` | string  | N/A | N/A |  | Only available when Type is JWT SSO.  |
  | `createdTime` | datetime  | N/A | N/A |  |  |
  | `createdBy` | [Agent](#Agent-Object)  | N/A | N/A |  | Which agent create the current item. |
  | `lastUpdatedTime` | datetime  | N/A | N/A |  |  |
  | `lastUpdatedBy:` | [Agent](#Agent-Object)  | N/A | N/A |  | Which agent update the current item last time. |

### Agent SSO Endpoints

#### Get Agent SSO

  `GET /api/v3/livechat/agentSSO`

##### Response

the response is: [Agent SSO](#Agent-SSO-Object) Object

#### Update Agent SSO

  `PUT /api/v3/livechat/agentSSO`

##### Parameters

Request Body

  The request body contains data with the [Agent SSO](#Agent-SSO-Object) structure

##### Response

the response is: [Agent SSO](#Agent-SSO-Object) Object

## Visitor SSO

  You need `Manage Settings` permission to setting sso for a site.

- `GET /api/v3/livechat/visitorSSO` -Get SSO settings of visitor
- `PUT /api/v3/livechat/visitorSSO`  -Update configuration of visitor

### Related Object Json Format

#### Visitor SSO Object

  Visitor SSO Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `isEnabled` | boolean  | N/A | N/A |  |  |
  | `loginURL` | string  | N/A | N/A |  |  |
  | `logoutURL` | string  | N/A | N/A |  |  |
  | `changePasswordURL` | string  | N/A | N/A |  |  |
  | `certificateFileName` | string  | N/A | N/A |  |  |
  | `fieldMappings` | [Agent](#Field-Mapping-Object)[]  | N/A | N/A |  |   |
  | `perCampaign` | [Agent](#Agent-Object)[]  | N/A | N/A |  |   |

#### Field Mapping Object

Data Mapping is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only | Mandatory | Default | Description |
  | - | - | :-: | :-: | - |
  | `attribute` | string  | N/A | yes | SSO attribute name. |
  | `comm100FieldId` | Guid  | N/A | yes | Id of the Comm100 field. |

#### Campaign SSO Options Object

SignIn Options is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only | Mandatory | Default | Description |
  | - | - | :-: | :-: | - |
  | `campaignId` | Guid  | yes | N/A | Id of the campaign. |
  | `signInOption` | string  | N/A | N/A | Type of the sign in, including `no`, `optional` and `required`. |
  | `isPrechatFromSkipped` | boolean  | N/A | N/A | Whether the pre-chat form is skipped when visitors sign in. |

### Visitor SSO Endpoints

#### Get Visitor SSO

  `GET /api/v3/livechat/visitorSSO`

##### Parameters

Query string

  | Name  | Type | Required | Default | Description |
  | - | - | :-: | :-: | - |
  | `include` | string | no  | |  Available value: `campaign`,`field` |

##### Response

the response is: [Visitor SSO](#Visitor-SSO-Object) Object

#### Update Visitor SSO

  `PUT /api/v3/livechat/visitorSSO`

##### Parameters

Request Body

  The request body contains data with the [Visitor SSO](#Visitor-SSO-Object) structure

##### Response

the response is: [Visitor SSO](#Visitor-SSO-Object) Object

## Shift

  You need `Manage Settings` permission to manage shift.

- `GET /api/v3/livechat/shift` - get a list of shift
- `GET /api/v3/livechat/shift/{id}` - get a single shift
- `POST /api/v3/livechat/shift` - create a new shift
- `PUT /api/v3/livechat/shift/{id}` - update a shift
- `DELETE /api/v3/livechat/shift/{id}` - remove a shift

### Related Object Json Format

#### Shift Object

  Shift Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  |`id` | Guid  | | yes | N/A | | Id of the current item.  |
  | `name` | string  | N/A | N/A |  | Name of the shift. |
  | `timeZone` | boolean  | N/A | N/A |  |  |
  | `holiday` | [Holiday](#Holiday-Object)[]  | N/A | N/A | 0 | |
  | `member` | [Agent](#Agent-Object)[] or [Department](#Department-Object)[]  | N/A | N/A | 0 |  |
  | `workingHours` | [Working Hours](#Working-Hours-Object)[]  | N/A | N/A | 0 |  |

#### Holiday Object

  Holiday Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `name` | string  | N/A | N/A |  |  |
  | `holiday` | date  | N/A | N/A |  |  |

#### Working Hours Object

  Working Hours Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `dayofWeek` | string  | N/A | N/A |  |  |
  | `startTime` | datetime  | N/A | N/A |  |  |
  | `endTime` | datetime  | N/A | N/A |  |  |
  | `awayStatus` | [Custom Agent Away Status](#Custom-Agent-Away-Status-Object)  | N/A | N/A |  |  |

### Shift Endpoints

#### Get all Shift a site

  `GET /api/v3/livechat/shift`

##### Response

the response is: [Shift](#Shift-Object) Object

#### Get a Shift by id

  `GET /api/v3/livechat/shift/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the shift |

##### Response

the response is: [Shift](#Shift-Object) Object

#### Create a new Shift

  `POST /api/v3/livechat/shift`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the shift |

Request Body

  The request body contains data with the [Shift](#Shift-Object) structure

##### Response

the response is: [Shift](#Shift-Object) Object

#### Update a Shift

  `PUT /api/v3/livechat/shift/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the shift |

Request Body

  The request body contains data with the [Shift](#Shift-Object) structure

##### Response

the response is: [Shift](#Shift-Object) Object

#### Delete a Shift by id

  `DELETE /api/v3/livechat/shift/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique Id of the shift |

##### Response

HTTP/1.1 204 No Content

## Campaigns

### Related Object Json Format

#### Campaign Object

  Campaign Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  |`id` | Guid  | | yes | N/A | | Id of the current item.  |
  | `name` | string  | N/A | N/A |  | Name of the shift. |
  | `description` | string  | N/A | N/A |  |  |

#### Chat Button Object

  Chat Button Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `type` | string | N/A | yes |  | Type of the button, including `adaptive`, `image` and `textLink`. |
  | `isHideWhenOffline` | boolean | N/A | N/A |  | Whether the chat button is visible when no agent is online.`true` means that button is invisible. |
  | `isDomainRestrictionEnabled` | boolean | N/A | N/A |  | Whether the domain restriction is enabled or not. |
  | `allowedDomains` | string | N/A | N/A |  | An array of domains/urls, on which the chat button is visible. |
  | `adaptiveButtonColor` | string | N/A | N/A |  | The theme color of the chat button, available when `type` is `adaptive`. |
  | `adaptiveButtonIconType` | integer | N/A | N/A |  | Type of the chat button icon, including `1`, `2` , `3` and `4`, available when `type` is `adaptive`. |
  | `adaptiveButtonOnlineIcon` | string | N/A | N/A |  | File key of the chat online button, available when `type` is `adaptive`. |
  | `adaptiveButtonOfflineIcon` | string | N/A | N/A |  | File key of the chat offline button, available when `type` is `adaptive`. |
  | `isImageButtonFloating` | boolean | N/A | N/A |  | Whether the image button is float or not, available when `type` is `image`. |
  | `imageButtonPosition` | string | N/A | N/A |  | Position of the image button, including `centered`, `topLeft`, `topMiddle`, `topRight`, `bottomLeft`, `bottomMiddle`, `bottomRight`, `leftMiddle` and `rightMiddle`, available when `type` is `image`. |
  | `imageButtonPositionMode` | string | N/A | N/A |  | Position mode of the image button, including `Basic` and `Advanced`, available when `type` is `image`. |
  | `isImageButtonXOffsetByPixel` | boolean | N/A | N/A |  |                 available when `type` is `image`. |
  | `imageButtonXOffset` | integer | N/A | N/A |  |  If Is XOffset By Pixel is True, it represents the offset pixel value of the X coordinate. If Is XOffset By Pixel is False, it represents the offset percentage value of the X coordinate, available when `type` is `image`. |
  | `isImageButtonYOffsetByPixel` | boolean | N/A | N/A |  |                 available when `type` is `image`. |
  | `imageButtonYOffset` | integer | N/A | N/A |  |  If Is YOffset By Pixel is True, it represents the offset pixel value of the Y coordinate. If Is YOffset By Pixel is False, it represents the offset percentage value of the Y coordinate, available when `type` is `image`. |
  | `imageButtonImageSource` | string | N/A | N/A |  |  Type of the image source, including `fromGallery` or `fromMyComputer` |
  | `imageButtonOnlineImage` | string | N/A | N/A |  | File key of the image online button, available when `type` is `image`. |
  | `imageButtonOfflineImage` | string | N/A | N/A |  | File key of the image offline button, available when `type` is `image`. |
  | `imageButtonTypeOnMobile` | string | N/A | N/A |  | The type of button on mobile device, including `text` and `image`, available when `type` is `image`. |
  | `imageButtonColorOnMobile` | string | N/A | N/A |  |  |
  | `imageButtonTextColorOnMobile` | string | N/A | N/A |  | The theme color of chatbutton on mobile device. |
  | `imageButtonOnlineImageOnMobile` | string | N/A | N/A |  | The file key of image on mobile device when any agents is online. |
  | `imageButtonOfflineImageOnMobile` | string | N/A | N/A |  | The file key of image on mobile device when no agent is online. |
  | `imageButtonPositionOnMobile` | string | N/A | N/A |  | Position of the chat button on mobile device, including `bottomLeft`, `bottomMiddle`, `bottomRight`, `leftMiddle`, `RightMiddle`, `leftBottom` and `rightBottom`. |
  | `imageButtonTypeOnMobile` | string | N/A | N/A |  | the content of the text link, available when `type` is `textLink`. |

#### Chat Window Object

  Chat Window Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `width` | integer | N/A | N/A |  |  |
  | `height` | integer | N/A | N/A |  |  |
  | `style` | string | N/A | yes |  |  Style of the window's theme, including `classic`, `circle` and `bubble`. |
  | `color` | string | N/A | yes |  |  Color of the window's theme. |
  | `type` | string | N/A | yes |   | Type of the chat window, including `embedded` and `popup`. |
  | `headerType` | string | N/A | N/A |  |  Type of the header, including `agentInfo`, `bannerImage` and `avatarAndLogo` when `style` is `classic`. |
  | `isAvatarDisplayed` | boolean | N/A | N/A |   | Whether the avatar of the agent is visible or not, available when  `headerType` is `agentInfo` or `avatarAndLogo`. |
  | `isTitleDisplayed` | boolean | N/A | N/A |   | Whether the title of the agent is visible or not, available when `headerType` is `agentInfo`. |
  | `isBioDisplayed` | boolean | N/A | N/A |   | Whether the bio of the agent is visible or not, available when `headerType` is `agentInfo`. |
  | `isLogoDisplayed` | boolean | N/A | N/A |   | Whether the logo is visible or not, available when `headerType` is `avatarAndLogo`. |
  | `logo` | string | N/A | N/A |  | File key of the logo. |
  | `bannerImage` | string | N/A | N/A |  | File key of the banner image, available when `headerType` is `bannerImage`. |
  | `isAvatarDisplayedWithMessage` | boolean | N/A | N/A   | | Whether the avatar of the agent is visible or not in the message body, available when `style` is `classic`or `simple`. |
  | `isBackgroundDisplayed` | boolean | N/A | N/A |  |  Whether the texture and picture of the background is visible or not in the message body, available when `style` is `classic`or `simple`. |
  | `backgroundTexture` | integer | N/A | N/A |  |  |
  | `customCSSOfClassic` | string | N/A | N/A |  |  The content of custom css when  `style` is `classic`. |
  | `customCSSOfCircle` | string | N/A | N/A |  |  The content of custom css when  `style` is `circle`. |
  | `isTranscriptDownloadAllowed` | boolean | N/A | N/A |   | Whether the visitor can download the chat transcript. |
  | `isTranscriptPrintAllowed` | boolean | N/A | N/A |   | Whether the visitor can print the chat transcript. |
  | `isTranscriptSentToVisitors` | boolean | N/A | N/A |   | Whether the transcript send to visitor. |
  | `isTranscriptSentFromCurrentAgentEmail` | boolean | N/A | N/A |   | Available when `isTranscriptDownloadAllowed` is true. |
  | `fromEmailName` | string | N/A | N/A |  |  The from name for sending transcript email, available when `isTranscriptSentFromCurrentAgentEmail` is true. |
  | `fromEmailAddress` | string | N/A | N/A |  |  The subject address for sending transcript email, available when `isTranscriptSentFromCurrentAgentEmail` is true. |
  | `isSMTPServerCustomized` | boolean | N/A | N/A |   | Whether use custome SMTP server. |
  | `customSMTPServer.fromName` | string | N/A | N/A |   |  |
  | `customSMTPServer.fromEmail` | string | N/A | N/A |   |  |
  | `customSMTPServer.mailServer` | string | N/A | N/A |   |  |
  | `customSMTPServer.port` | integer | N/A | N/A |   |  |
  | `customSMTPServer.encryptedType` | string | N/A | N/A |   | Including `none`, `SSL` and `TLS`.  |
  | `customSMTPServer.IsAuthenticationRequired` | boolean | N/A | N/A |   |  |
  | `customSMTPServer.username` | string | N/A | N/A |   |  |
  | `customSMTPServer.password` | string | N/A | N/A |   |  |
  | `isSwitchToOfflineMessageAllow` | boolean | N/A | N/A |   | Allow visitors to switch to Offline Message Window while waiting for chat. |
  | `isFileSendAllow` | boolean | N/A | N/A |   | Whether the agent can send file or not. |
  | `ifMarkUnreadMessage` | boolean | N/A | N/A |   |  |
  | `isAudioChatEnabled` | boolean | N/A | N/A |   | Whether the agent can use audio chat. |
  | `isVideoChatEnabled` | boolean | N/A | N/A |   | Whether the agent can use video chat. |
  | `isBrowserPopupNotificationEnabled` | boolean | N/A | N/A |   | It is available for private server sites. For shared server clients, the push notification is disabled by default. |
  | `ifEndChatWhenVisitorIsInactive` | boolean | N/A | N/A |   | Automatically end chats if visitors don't respond in period of time. |
  | `minutesOfVisitorInactivity` | integer | N/A | N/A |  |  |
  | `isTranscriptSentForArchiving` | boolean | N/A | N/A |  |  |
  | `receivingEmailAddressesForArchivingTranscripts` | string | N/A | N/A |   |  |
  | `emailSubjectForArchivingTranscripts` | string | N/A | N/A |   |  |
  | `greetingMessage` | string | N/A | N/A |   |  |
  | `isCustomJSEnabled:` | boolean | N/A | N/A |   |  |
  | `customJS` | string | N/A | N/A |   |  |

#### PreChat Object

  PreChat Window Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `isEnable` | boolean | N/A | N/A |   | Whether the pre-chat is enabled or not. |
  | `isTeamNameDisplayed` | boolean | N/A | N/A |   | Whether the team name is visible or not in the header. |
  | `teamName` | string | N/A | N/A |  | The team name displayed in the header. |
  | `isAgentAvatarDisplayed` | boolean | N/A | N/A   | | Whether the avatar of the agent is visible or not in the header. |
  | `greetingMessage` | string | N/A | N/A |  |   |
  | `socialMediaLogin` | string | N/A | N/A |  |  Including `none` and `facebook`. |
  | `field` | [field](#Campaign-Form-Field-Object)[] | N/A | N/A |  | These System Fields are prebuilt and can’t be deleted: `name`, `email`, `phone`, `company`, `product service`, `department`, `ticket id`.  |
  | `isVisitorInfoRecorded` | boolean | N/A | N/A | true | If remember visitor info collected from pre-chat form. |
  | `formFieldLayoutStyle` | string | N/A | N/A |   | Including `leftofInput` and `aboveInput`. Available for Post Chat and Offline Message forms.  |

#### Campaign Form Field Object

  Campaign Form Field is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `id` | Guid | yes | N/A |   | Id of the current item. |
  | `field` | [type](#Live-Chat-Field-Object) | N/A | N/A |   |  |
  | `isVisible` | boolean | N/A | N/A |   | Whether the field is visible or not. |
  | `isRequired` | boolean | N/A | N/A |   | Whether the field is required or not when submitting the form |
  | `order` | integer | N/A | N/A |   | The order of the field. |
  | `ratingGrade` | [type](#Rating-Grade-Object) | N/A | N/A |   |  |

#### Rating Grade Object

  Rating Grade is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `id` | Guid | yes | N/A | Id of the current item. |
  | `grade` | integer | N/A | N/A |  |  |
  | `label` | string | N/A | N/A |  |  |
  | `isVisible` | boolean | N/A | N/A |  |  |

#### Live Chat Field Object

  Live Chat Field is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `id` | Guid | yes | N/A |  | Id of the current item. |
  | `isSystem` | boolean | N/A | N/A |  | whether the field is system or not. |
  | `name` | string | N/A | N/A |  |  |
  | `type` | string | N/A | N/A |  | The [Live Chat Field Type](#Live-Chat-Field-Type) of the field. |
  | `option` | [Live Chat Field Option](Live-Chat-Field-Option)[] | N/A | N/A |  | Live Chat Field Option, available whey Type is `radioBox`, `dropdownList`, `checkboxList`. |
  | `leftText` | string | N/A | N/A |  | Available whey Type is NPS. |
  | `rightText` | string | N/A | N/A |  | Available whey Type is NPS. |
  | `optionGroup` | [Live Chat Field Option Group](Live-Chat-Field-Option-Group)[] | N/A | N/A |  | Live Chat Field Option Group, available whey Type is `checkboxListwithOptionGroups`. |

#### Live Chat System Field

  Live Chat System Field is one key of the following keys:

  | System Field | Type | Only Available Forms | Is Required |
  | - | - | :-: | - |
  | `name` | Text Box | Name field, `Pre Chat Form` or `Offline Message Form` only. |
  | `email` | Text Box | Email field, `Pre Chat Form` or `Offline Message Form` only. |
  | `phone` | Text Box | Phone field, `Pre Chat Form` or `Offline Message Form` only. |
  | `company` | Text Box | Company field, `Pre Chat Form` or `Offline Message Form` only. |
  | `product service` | Dropdown List | Product and Service field, `Pre Chat Form` only. |
  | `department` | Dropdown List | Department field, `Pre Chat Form` or `Offline Message Form` only. |
  | `ticket id` | Text Box | Ticket field, `Pre Chat Form` or `Offline Message Form` only.  |
  | `rating` | Rating | Rating field, `Post Chat Form` only. |
  | `rating comment` | Text Area | Comments field, `Post Chat Form` only. |
  | `subject` | Text Box | Subject field, `Offline Message Form` only. |
  | `message` | Text Area | Content field, `Offline Message Form` only. |
  | `attachment` | File | Attachment field, `Offline Message Form` only. |
  | `category` | Dropdown List or Checkbox List with Groups  | category field , `agent wrap-up` only |
  | `wrapup comment` | Text Area | comment field , `agent wrap-up` only |

#### Live Chat Field Type

  Live Chat Field Type is one key of the following keys:

  | Name | Available Forms |
  | - | :-: | - |
  | `textBox` | `Pre-Chat`, `Post Chat`, `Offline Message`, `Agent Wrap-Up`   |
  | `textArea` | `Pre-Chat`, `Post Chat`, `Offline Message`, `Agent Wrap-Up`   |
  | `radioBox` | `Pre-Chat`, `Post Chat`, `Offline Message`, `Agent Wrap-Up`   |
  | `checkbox` | `Pre-Chat`, `Post Chat`, `Offline Message`, `Agent Wrap-Up`   |
  | `dropdownList` | `Pre-Chat`, `Post Chat`, `Offline Message`, `Agent Wrap-Up` |
  | `checkboxList` | `Pre-Chat`, `Post Chat`, `Offline Message`, `Agent Wrap-Up` |
  | `NPS` | `Post Chat`  |
  | `file` | `Offline Message`   |
  | `rating` | `Post Chat` |
  | `checkboxListwithOptionGroups` | `Agent Wrap-Up`   |

#### Live Chat Field Option

  Live Chat Field Option is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `value` | string | N/A | N/A |  |  |
  | `order` | integer | N/A | N/A |  |  |

#### Live Chat Field Option Group

  Live Chat Field Option Group is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `name` | string | N/A | N/A |  |  |
  | `order` | integer | N/A | N/A |  |  |
  | `option` | [Live Chat Field Option](Live-Chat-Field-Option)[]  | N/A | N/A |  |  |

#### Post Chat Object

  Post Chat Window Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `isEnable` | boolean | N/A | N/A |   | Whether the pre-chat is enabled or not. |
  | `field` | [field](#Campaign-Form-Field-Object)[] | N/A | N/A |  | These System Fields are prebuilt and can’t be deleted: `rating`, `rating comment`.  |
  | `greetingMessage` | string | N/A | N/A |  |   |
