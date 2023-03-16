---
title: Portfolio
---

# Portfolio

This API lets you retrieve holdings and positions in your portfolio.

|Method	|API                |Detail                         |
|-------|-------------------|-------------------------------|
|POST	|	/holdings       |Retrieve the list of long term equity holdings
|POST	| /positions	    |Retrieve the list of short term positions
|POST	|/positions/convert	|Convert intraday to long term or long term to intraday 

## Holdings

Holdings contain the long term equity Holdings of the customer. All the financial instruments in the holdings reside in the customer’s DEMAT account indefinitely until its sold or is delisted or changed by the exchanges. Changes to DEMAT account is settled in T+1 days. 




__Request Structure__

```
{
    "userId": "<USER_ID>",
    "actId": "<USER_AC>",
    "prd": "C"
}
```
__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|           |
|actId	|String	|            |
|    prd| String|               |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "stat": "Ok",
            "poaStatus": 0,
            "holdingVal": {
                "isin": "INE593W01010",
                "buyPrice": "0",
                "totalQty": "5",
                "usedQty": "0",
                "sellableQty": 5,
                "colQty": "0",
                "btstQty": "0",
                "authQty": 0,
                "authDate": "",
                "netPnl": 0,
                "soldValue": "0.000000",
                "benQty": null,
                "unpledgedQty": "0",
                "tmColQty": "0",
                "dpQty": null,
                "pledgeQty": 0,
                "dayPnl": 0,
                "ltp": "0",
                "exDetails": [
                    {
                        "symbol": "FOCUS-EQ",
                        "exchange": "NSE",
                        "token": "6836",
                        "previousClose": "316.85"
                    }
                ]
            }
        }
 
    ]
}
```

__Parameters__

|Field	|Type	|Description|
|-------|-------------------|-------------------------------|
|isin	|String	|Exchange|
|buyPrice	|String	|Refer Trading Symbol at Page No|
|totalQty	|String	|Exchange standard id for each scrip. Refer here|
|usedQty	|String	|Universal standard id for each scrip|
|sellableQt |String	|Total quantities|
|colQty	    |String	|Quantities in delivered in demat account|
|btstQty	|String	|Quantities not delivered in demat account|
|authQty	|Int	|Quantities available for transactions|
|authDate	|String	|Quantities placed as collateral with broker|
|netPnl 	|Int|Average Buy Price of total quantities|
|soldValue  |String	|Refer Trading Symbol at Page No|
|benQty     |    String	|Refer Trading Symbol at Page No|                                                            
|unpledgedQty |       String	|Refer Trading Symbol at Page No|                                                            
|tmColQty   |      String	|Refer Trading Symbol at Page No|                                                            
|dpQty      |      String	|Refer Trading Symbol at Page No|                                                         
|pledgeQty  |     Int	|Refer Trading Symbol at Page No|                                                              
|dayPnl     |      Int	|Refer Trading Symbol at Page No|                                                          
|ltp        |      String	|Refer Trading Symbol at Page No|                                                       

## Positions



__Request Structure__

```
{
    "userId": "<USER_ID>",
    "actId": "<USER_AC>",
}
```
__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|           |
|actId	|String	|           |

__Response Structure__

```
{
    "status": "Ok",
    "message": "success",
    "result": [
        {
            "formattedInsName": "JPYINR 13JAN23 FUT",
            "tradingSymbol": "JPYINR13JAN23F",
            "exchange": "CDS",
            "segment": "cde_fo",
            "token": "11771",
            "product": "M",
            "netQty": "-2",
            "netBuyQty": "0",
            "netBuyAvgPrice": "0.0",
            "netBuyAvg": "NaN",
            "netBuyValue": "0.0",
            "netSellQty": "2",
            "netSellAvgPrice": "63.5675",
            "netSellAvg": "63567.5",
            "netSellValue": "127135.0",
            "averagePrice": "63.5675",
            "ltp": "61.6750",
            "pnl": "0.00",
            "mtm": "",
            "pdc": "61.67",
            "realizedpnl": "0.0",
            "unrealizedpnl": "3785.00",
            "multiplier": "1000",
            "lotSize": null,
            "tickSize": null
        }
     ]
 }
```
__Parameters__

|Field	| Type	            |Description                    |
|-------|-------------------|-------------------------------|
|formattedInsName|String   |User specific identification generated by nidhi|
|tradingSymbol   |String   |Refer Trading Symbol in Tables                 |
|exchange	     |String   |Exchange standard id for each scrip. Refer here|
|segment	     | String  |Position Type |
|token	         | String  |Exchange & Segment |
|product	     | String  |Product type |
|netQty    	     |float    |Average buy price|
|netBuyQty	     |Int	   |Total quantity bought|
|netBuyAvgPrice  |  String | ////  |                                                                                            
|netBuyAvg       |  String | ////  |                                                                                           
|netBuyValue     |  String | ////  |                                                                               
|netSellQty      |  String | ////  |                                                                                  
|netSellAvgPrice |  String | ////  |                                                                                             
|netSellAvg      |  String | ////  |                                                                                        
|netSellValue    |  String | ////  |                                                                                            
|averagePrice    |  String | ////  |                                                                                            
|ltp             |  String | ////  |                                                                                
|pnl             |  String | ////  |                                           
|mtm             |  String | ////  |                                                                           
|pdc             |  String | ////  |                                                              
|realizedpnl     |  String | ////  |                                                                                 
|unrealizedpnl   |  String | ////  |                                                                                         
|multiplier      |  String | ////  |                                                                                     
|lotSize         |  String   | ////  |                                                                               
|tickSize        |  String   | ////  |                                                                            


## Convert Position

__Request Structure__

```
{
    "userId": "<USER_ID",
    "actId": "<ACT_ID",
    "exchange": "NSE",
    "tradingSymbol": "ZOMATO-EQ",
    "qty": "1",
    "product": "I",
    "prevProduct": "M",
    "tranType": "B",
    "posType": "DAY"
}
```
__Parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId|	String|	User specific identification generated by nidhi|
|actId| String|	Refer Trading Symbol in Tables |
|exchange| String|	Exchange standard id for each scrip |
|tradingSymbol| String|	Position Type |
|qty|	String|	Exchange standard id for each scrip. Refer here|
|product|	String|	Refer Trading Symbol in Tables|
|prevProduct|	Int|	No of shares modification is desired|
|tranType| String|	Desired product type |
|posType| String|	Desired product type |



