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
|availableMargin	|Int	|User specific identification generated by nidhi|
|openingBalance	|Int	|Available amount to trade|
|marginUsed	|Int	|Start of the day amount|
|payin	|Int	|Amount received against collateral|
|stockPledge	|Int	|Amount available against selling deliveries|
|holdingSellCredit	|Int	|Amount utilised in the day|
|brokerage	|Int	|Amount blocked against payout request|
|exposure	|Int	|Amount available to withdraw in bank account|
|span	|Int	|Available amount to trade|
|premium	|Int	|Available amount to trade|



