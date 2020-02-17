# API

## Summary

- [Visitor](#Visitor)
- [Custom Agent Away Status](#Custom-Agent-Away-Status)

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
  | `id` | Guid | yes  |  the unique id of the visitor |

##### Response

the response is: [Visitor](#Visitor-Object) Object

#### Update a visitors

  `PUT /api/v3/livechat/visitors/{id}`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique id of the visitor |

Request Body

  The request body contains data with the [Visitor](#Visitor-Object) structure

##### Response

the response is: [Visitor](#Visitor-Object) Object

## Custom Agent Away Status Object

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
  | `name` | string  | N/A | yes |  | Name of the custom away status. |
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
  | `id` | Guid | yes  |  the unique id of the custom agent away status |

##### Response

the response is: [Custom Agent Away Status](#Custom-Agent-Away-Status-Object) Object

#### Create a new Custom Agent Away Status

  `POST /api/v3/livechat/customAwayStatus`

##### Parameters

Path Parameters

  | Name  | Type | Required  | Description |
  | - | - | - | - |
  | `id` | Guid | yes  |  the unique id of the custom agent away status |

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
  | `id` | Guid | yes  |  the unique id of the custom agent away status |

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
  | `id` | Guid | yes  |  the unique id of the custom agent away status |

##### Response

HTTP/1.1 204 No Content
