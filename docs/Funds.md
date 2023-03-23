---
title: Funds
---


## Funds Limits

|Type	| API|Details	 |
|-------|------|-------------|
|POST	|funds/limits|	Place a new funds|


__Request Structure__

```
{
   "userId": "<USER_ID>",
   "accountId": "<USER_AC>"
}
```
__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|           |
|accountId	|String	|            |

__Response Structure__
```
{
    "status": "Ok",
    "message": null,
    "result": [
        {
            "availableMargin": 1000000.0,
            "openingBalance": 1000000.0,
            "marginUsed": 0.0,
            "payin": 0.0,
            "stockPledge": 0.0,
            "holdingSellCredit": 0.0,
            "brokerage": 0.0,
            "exposure": 0.0,
            "span": 0.0,
            "premium": 0.0
        }
    ]
}
```

__Parameters__

|Field	|Type	|Description|
|-|-|-|
|availableMargin	|Int	|Account Holder's Available Margin is dispalyed|
|openingBalance	|Int	|Account Holder's Opening Balance is displayed|
|marginUsed	|Int	|Account Holder's Margin Used is displayed|
|payin	|Int	|Payin is the funds transferred by the customer from his bank account into his trading account|
|stockPledge	|Int	||
|holdingSellCredit	|Int	||
|brokerage	|Int	||
|exposure	|Int	|The exposure margin is charged over and above the SPAN margin, and is usually done so at the discretion of the broker|
|span	|Int	|SPAN determines margin requirements based on a global assessment of the one-day risk for a trader's account|
|premium	|Int	| |




