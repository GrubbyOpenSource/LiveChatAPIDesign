# API

## Summary

- Chatbot
  - [chatbot subscription](#chatbot-subscription)
  - [chatbot language](#chatbot-language)

## Chatbot Subscription

- `GET /api/v3/ia/chatbot/subscription` - [Get chatbot subscription](#get-chatbot-subscription)

### Related Object Json Format

#### Chatbot Subscription Object

  Chatbot Subscription Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | - |
  | `isChatbotEnabled` | bool  | N/A | N/A | false | if the site is enabled chatbot |
  | `totalPurchasedMessageAmount` | integer | N/A | N/A | 0 | It is the maximum available amount of the chatbot messages in this month. |
  | `startDate` | Date | N/A | N/A | | the chatbot subscription start date |
  | `nextRenewDate` | Date | N/A | N/A | | next renew date |
  | `messageQuotaPerMonth` | integer | N/A | N/A | 0 | message quota per month |
  | `paymentPeriod` | string  | N/A | N/A | Monthly | enums: `Monthly`,`Quarterly`, `Yearly` |
  | `monthlyPrice` | float  | N/A | N/A | 0 | monthly price |
  | `quarterlyPrice` | float  | N/A | N/A | 0 | quarterly price |
  | `yearlyPrice` | float  | N/A | N/A | 0 | yearly price |
  | `overageUnitPrice` | float  | N/A | N/A | 0 | overage unit price |
  | `overageMessageQuota` | integer  | N/A | N/A | 0 | overage message quota |
  | `chatbotUsages` | [ChatbotUsage](#Chatbot-Usage-Object)[]  | N/A | N/A | | an array of [ChatbotUsage](#Chatbot-Quota-Object) Objects  |

#### Chatbot Usage Object

  Chatbot Usage Object is represented as simple flat JSON objects with the following keys:  

  | Name | Type | Include | Read-only For Put | Mandatory For Post | Default | Description |
  | - | - | :-: | :-: | :-: | :-: | - |
  | `botId` | Guid  | | N/A | N/A | | id of the bot |
  | `usedMessageAmount` | double  | | N/A | N/A | 0 | used message amount of the bot |
  | `bot` | [Bot](#bot-Object)  | yes | N/A | N/A | | Available only when bot is included |

### Endpoints

#### Get chatbot subscription

  `GET /api/v3/ia/chatbot/subscription`

##### Parameters
  
Query string

  | Name  | Type | Required | Default | Description |
  | - | - | :-: | :-: | - |
  | `include` | string | no  | |  Available value: `bot` |

##### Response

the response is: [Chatbot Subscription](#Chatbot-Subscription-Object) Object
just a test