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
|userId	|String	|The unique, permanent user ID registered with the broker           |
|actId	|String	| Users Logged in ID will be displayed         |
|prd    | String|           |

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
|isin	|String	|The standard ISIN representing stocks listed on multiple exchanges|
|buyPrice	|String	|Segment Buy Price|
|totalQty	|String	|Total Quantity of position / Holdings|
|usedQty	|String	|Used Quantity of position / Holdings|
|sellableQt |String	|Sell able quantity of Holding / Position|
|colQty	    |String	||
|btstQty	|String	||
|authQty	|Int	||
|authDate	|String	||
|netPnl 	|Int|Net Profit and Loss Value|
|soldValue  |String	||
|benQty     |    String	||                                                            
|unpledgedQty |       String	||                                                            
|tmColQty   |      String	||                                                            
|dpQty      |      String	||                                                         
|pledgeQty  |     Int	||                                                              
|dayPnl     |      Int	| Day Profit and Loss will be displayed|                                                          
|ltp        |      String	|Last trade price of the scrip. The price at which the final trade happens between a buyer and a seller|                                                       

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
|userId	|String	|The unique, permanent user ID registered with the broker           |
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
|formattedInsName|String   |  |
|tradingSymbol   |String   | Exchange tradingsymbol of the of the instrument           |
|exchange	     |String   |Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)     |
|segment	     | String  |Segment is ( EQ , FUT , PE , CE )    |
|token	         | String  |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details             |
|product	     | String  | Product code (MIS or CNC or NRML)            |
|netQty    	     |float    | Number of quantity            |
|netBuyQty	     |Int	   |Net Buy Quantity   |
|netBuyAvgPrice  |  String | Ney Buy Average Price  |                                                                                            
|netBuyAvg       |  String | Net Buy Average  |                                                                                           
|netBuyValue     |  String | Net Buy Value  |                                                                               
|netSellQty      |  String | Net Sell Quantity  |                                                                                  
|netSellAvgPrice |  String | Net Sell Average Price  |                                                                                             
|netSellAvg      |  String | Net Sell Average  |                                                                                        
|netSellValue    |  String | Net Sell Value  |                                                                                            
|averagePrice    |  String | Average Price for Position  |                                                                                            
|ltp             |  String | Last trade price of the scrip. The price at which the final trade happens between a buyer and a seller  |                                                                                
|pnl             |  String | Profit and Loss  |                                           
|mtm             |  String | Market to Market  |                                                                           
|pdc             |  String | Previce Day Close Value  |                                                              
|realizedpnl     |  String | ////  |                                                                                 
|unrealizedpnl   |  String | The Number of shares got unfilled  |                                                                                         
|multiplier      |  String | The Multiplier Of Scrip  |                                                                                     
|lotSize         |  String   | Quantity of a single lot  |                                                                               
|tickSize        |  String   | Ticker Size Of The Scrip (in paisa).Tick size is the minimum price change between different bid and offer prices of an asset traded on an exchange platform  |                                                                            


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
|userId|	String|	|
|actId| String| |
|exchange| String|	 |
|tradingSymbol| String|	 |
|qty|	String|	|
|product|	String|	|
|prevProduct|	Int|	|
|tranType| String|	 |
|posType| String|	 |



