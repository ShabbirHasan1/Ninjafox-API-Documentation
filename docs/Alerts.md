---
title: Alerts
---

| Type | API                 | Details                    |
| ---- | ------------------- | -------------------------- |
| POST | alerts/set          | Set alerts Request         |
| POST | alerts/get          | Get  pending alerts        |
| POST | alerts/modify       | Modify alerts              |
| POST | broker/getbrokermsg | Get broker message         |
| POST | alerts/cancel       | Cancel alerts              |
| POST | exch/exchstatus     | Exchange status            |
| POST | exch/exchmsg        | Exchange message           |
| POST | alerts/get/criteria | Get criteria for drop down |

### Set Alerts

__Request Structure__

```
{
    "userId": "<USER_ID",
    "tradingSymbol": "INFY-EQ",
    "exchange": "NSE",
    "alertCriteria": "LTP",
    "alertVersus": "52week high",
    "condition": ">",
    "validity": "GTT",
    "data": "60",
    "remarks": "INFY",
    "smsFlag": "",
    "mailFlag": "",
    "pushFlag": ""
}
```
__Input parameters__

| Field         | Type   | Description |
| ------------- | ------ | ----------- |
| userId        | String |             |
| tradingSymbol | String |             |
| exchange      | String |             |
| alertCriteria | String |             |
| alertVersus   | String |             |
| condition     | String |             |
| alertType     | String |             |
| validity      | String |             |
| data          | String |             |
| remarks       | String |             |
| smsFlag       | String |             |
| mailFlag      | String |             |
| pushFlag      | String |             |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "alertId": "23022300000001"
        }
    ]
}
```  
__Parameters__

| Field     | Type   | Description |
| --------- | ------ | ----------- |
| alertType | String |             |


### GetPendingAlerts

__Request Structure__

```
{
    "userId": "<USER_ID>"
}
```
__Input parameters__

| Field  | Type   | Description |
| ------ | ------ | ----------- |
| userId | String |             |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "alertType": "LTP_A_52HIGH",
            "alertId": "23021700000001",
            "tradingSymbol": "INFIBEAM-EQ",
            "exchange": "NSE",
            "token": "16249",
            "remarks": "Ragulan",
            "validity": "GTT",
            "data": "15.80",
            "alertCriteria": "LTP",
            "condition": ">",
            "alertVersus": "52week high"
        }
    ]
}
```
__Parameters__

| Field         | Type   | Description |
| ------------- | ------ | ----------- |
| alertType     | String |             |
| alertId       | String |             |
| tradingSymbol | String |             |
| exchange      | String |             |
| token         | String |             |
| remarks       | String |             |
| validity      | String |             |
| data          | String |             |
| alertCriteria | String |             |
| condition     | String |             |
| alertVersus   | String |             |


   
### ModifyAlerts

__Request Structure__

```
{
    "userId": "<USER_ID>",
    "actId": "<USER_Ac>",
    "exchange": "MCX",
    "tradingSymbol": "ZOMATO-EQ",
    "qty": "1",
    "price": "52",
    "product": "I",
    "tranType": "B",
    "priceType": "LMT",
    "ret": "DAY",
    "triggerPrice": "",
    "disclosedQty": "",
    "mktProtection": "",
    "bookProfitPrice": "",
    "bookLossPrice": "",
    "trailingPrice": ""
}
```
__Input parameters__

| Field           | Type   | Description |
| --------------- | ------ | ----------- |
| userId          | String |             |
| actId           | String |             |
| exchange        | String |             |
| tradingSymbol   | String |             |
| qty             | String |             |
| price           | String |             |
| product         | String |             |
| tranType        | String |             |
| prcType         | String |             |
| ret             | String |             |
| amo             | String |             |
| triggerPrice    | String |             |
| disclosedQty    | String |             |
| mktProtection   | String |             |
| bookProfitPrice | String |             |
| bookLossPrice   | String |             |
| trailingPrice   | String |             |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "alertId": "23021500000001"
        }
    ]
}
```
__Parameters__

| Field   | Type   | Description |
| ------- | ------ | ----------- |
| alertId | String |             |


### GetBrokerMsg

__Request Structure__

```
{
    "userId": "<USER_ID>"
}
```
__Input parameters__

| Field  | Type   | Description |
| ------ | ------ | ----------- |
| userId | String |             |
                          

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "time": "2023-02-23 11:25:39",
            "msgType": null,
            "message": "Invalid Oi",
            "note": "23012300000003",
            "msgSubType": "8"
        }
    ]
}
```
__Parameters__

| Field      | Type   | Description |
| ---------- | ------ | ----------- |
| alertType  | Date   |             |
| msgType    | String |             |
| message    | String |             |
| note       | String |             |
| msgSubType | String |             |



### CancelAlerts

__Request Structure__

```
{
    "userId": "<USER_ID>",
    "alertId": "23013000000008"
}
```
__Input parameters__

| Field   | Type   | Description |
| ------- | ------ | ----------- |
| userId  | String |             |
| alertId | String |             |


__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "alertId": "23021500000001"
        }
    ]
}
```
__Parameters__

| Field   | Type   | Description |
| ------- | ------ | ----------- |
| alertId | String |             |

### ExchStatus 

__Request Structure__

```
{
    "userId" : "<USER_ID",
} 
```
__Input parameters__

| Field  | Type   | Description |
| ------ | ------ | ----------- |
| userId | String |             |

                          

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "exchange": "NFO",
            "status": "CLOSED",
            "type": "NORMAL"
        }
    ]
}
```
__Parameters__

| Field    | Type   | Description |
| -------- | ------ | ----------- |
| exchange | String |             |
| status   | String |             |
| type     | String |             |


### EXchMsg

__Request Structure__

```
{
    "userId" : "<USER_ID",
    "exchange" : "NSE"
}
```
__Input parameters__

| Field    | Type   | Description |
| -------- | ------ | ----------- |
| userId   | String |             |
| exchange | String |             |


                          

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
          {
            "message": "The revised price range for OPTCUR GBPINR 27 JAN 2023 102.5000 PE is: 0.4075 - 3.5450",
            "time": "25-01-2023 16:28:59",
            "exchange": "CDS"
        }
    ]
}
```
__Parameters__

| Field    | Type   | Description |
| -------- | ------ | ----------- |
| message  | String |             |
| time     | Date   |             |
| exchange | String |             |

### Get Criterial


__Request Structure__

```
{
    "userId" : "<USER_ID"
}
```
__Input parameters__

| Field  | Type   | Description |
| ------ | ------ | ----------- |
| userId | String |             |


                          

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "createdOn": "2023-02-15T15:43:23.000+00:00",
            "alertCriteria": "LTP",
            "condition": ">",
            "alertVersus": null,
            "alertType": "LTP_A"
        }
    ]
}
```
__Parameters__

| Field         | Type   | Description |
| ------------- | ------ | ----------- |
| createdOn     | String |             |
| alertCriteria | Date   |             |
| condition     | String |             |
| alertVersus   | String |             |
| alertType     | String |             |

