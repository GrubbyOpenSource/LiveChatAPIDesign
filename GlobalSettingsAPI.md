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
  | `numberOfVisits` | int  | N/A | N/A | 0 | The total number of web pages the visitor viewed on your website. |
  | `numberOfChats` | int  | N/A | N/A | 0 | The total times of chats a visitor has made on your website from the first time to present. |
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
  | `order` | int  | N/A | N/A | 0 | The order of the custom away status. |

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
  | `attribute` | string  | no | yes | SSO attribute name. |
  | `comm100FieldId` | Guid  | no | yes | Id of the Comm100 field. |

#### Campaign SSO Options Object

SignIn Options is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only | Mandatory | Default | Description |
  | - | - | :-: | :-: | - |
  | `campaignId` | Guid  | yes | no | Id of the campaign. |
  | `signInOption` | string  | no | no | Type of the sign in, including `no`, `optional` and `required`. |
  | `isPrechatFromSkipped` | boolean  | no | no | Whether the pre-chat form is skipped when visitors sign in. |

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
