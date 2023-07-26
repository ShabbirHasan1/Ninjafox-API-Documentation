---
title: Funds
---


|Type	| Apis|Details	 |
|-------|------|-------------|
|POST	|funds/limits|	Place a new funds|
 

## Get Limits


Get all information of your trading account like balance, margin utilised, collateral, etc.



__Request Structure__

```
{
   "userId": "<USER_ID>",
   "accountId": "<USER_AC>",
}
```
__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|           |
|accountId	|String	|       |

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
|availableMargin	|int	|Account Holder's Available Margin is dispalyed|
|openingBalance	|int	|Account Holder's Opening Balance is displayed|
|marginUsed	|int	|Account Holder's Margin Used is displayed|
|payin	|int	|Payin is the funds transferred by the customer from his bank account into his trading account|
|stockPledge	|int	||
|holdingSellCredit	|int	||
|brokerage	|int	||
|exposure	|int	|The exposure margin is charged over and above the SPAN margin, and is usually done so at the discretion of the broker|
|span	|int	|SPAN determines margin requirements based on a global assessment of the one-day risk for a trader's account|
|premium	|int	||




