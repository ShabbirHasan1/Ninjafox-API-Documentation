---
title: Orders
---
# Orders

The order management API lets you place a new order, cancel or modify the pending order, retrieve the order status, trade status, order book & tradebook
                                                             
|Type	| API|Details	 |
|-------|------|-------------|
|POST	|order/execute     |	Place a new order|
|POST	|order/modify|	Modify a pending order|
|POST	|order/cancel|	Cancel a pending order|
|POST	|order/getmargin|	 get order margin|
|POST	|orderinfo/orderbook|	Retrieve the list of all orders for the day|
|POST	|orderinfo/tradebook	|Retrieve the list of all trades for the day|
|POST	|orderinfo/history	|get order history|


##  Place Order


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
    "amo": "",
    "triggerPrice": "",
    "disclosedQty": "",
    "mktProtection": "",
    "bookProfitPrice": "",
    "bookLossPrice": "",
    "trailingPrice": ""
}
```
__Input parameters__

|Field	|           Type	|                    Description|
|-------|-------------------|-------------------------------|
|userId|          String          | The unique, permanent user ID registered with the broker                       |                                   
|actId|           String         | Users Logged in ID will be displayed                      |                                   
|exchange|        String            |  Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)                      |                                  
|tradingSymbol|    String                |Exchange tradingsymbol of the of the instrument                        |                                   
|qty|           String         |Quantity to transact                        |                                 
|price|           String         | Price at which main leg of bracket order will be placed                       |                                 
|product|          String          |Product code (MIS or CNC or NRML)                        |                        
|tranType|          String          |Buy and Sell                        |                           
|prcType|            String        |	Price type(L or MKT or SL or SL-M)                        |                  
|ret|               String     |Retention type (from LoadRetentionType rest api).These orders state the system to keep the orders pending until the market price reaches the specified limit order price. The various retention orders are: Day or End of Session Order: This is the most commonly used retention type                        |         
|amo|   String |After Market Order                                |
|triggerPrice|String| The price at which an order should be triggered (SL, SL-M)                           |
|disclosedQty|String| Quantity to be disclosed (may be different from actual quantity) to the public exchange orderbook. Only for equitie                           |
|mktProtection|String|A market-with-protection order cancels an order to buy or sell stock or other assets and re-submits it as a limit order. A broker might submit a market-with-protection order if the price of the stock has moved unexpectedly and dramatically since the market order was placed.                          |
|bookProfitPrice|String|                        |      
|bookLossPrice|String|                         |
|trailingPrice|String|                         |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "requestTime": "16:25:08 31-01-2023",
            "orderNo": "23013100000051"
        }
    ]
}

```
__Parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|requestTime	|String	||
|orderNo	|String	||




##  Modify Order

__Request Structure__

```
{
    "userId": "<USER_ID>",
    "exchange": "NSE",
    "tradingSymbol": "ZOMATO-EQ",
    "orderNo": "23011900000017",
    "qty":"2",
    "ret": "DAY",
    "priceType": "MKT",
    "tranType": "B",
    "product": "I",
    "price": "0",
    "triggerPrice": "",
    "disclosedQty": "",
    "MktProtection": "",
    "bookProfitPrice": "",
    "bookLossPrice": "",
    "trailingPrice": ""
}
```
__Input parameters__

|Field|	Type|	Description|
|-------|-------------------|-------------------------------|
|userId|          String          | The unique, permanent user ID registered with the broker                       |                                   
|exchange |String	|Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX) |
|tradingSymbol |String	|Exchange tradingsymbol of the of the instrument|
|orderNo |String	|In case of BO & CO, which leg is modified `|
|qty|           String         |Quantity to transact                        |                                 
|ret |String	|Retention type (from LoadRetentionType rest api).These orders state the system to keep the orders pending until the market price reaches the specified limit order price. The various retention orders are: Day or End of Session Order: This is the most commonly used retention type|
|priceType	|String	|PriceType (Limit , Market , SL , SL-M) |
|tranType |String	|Buy and Sell|
|product |String	|Product code (MIS or CNC or NRML) |
|price |String	|Price at which main leg of bracket order will be placed |
|triggerPrice |String	| |
|disclosedQty |String	|Quantity to be disclosed (may be different from actual quantity) to the public exchange orderbook. Only for equitie |
|MktProtection |String	| |
|bookProfitPrice |String	| |
|bookLossPrice |String	| |
|trailingPrice |String	| |



__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "requestTime": "17:52:09 22-02-2023",
            "orderNo": "23022200000028"
        }
    ]
}
```
__Parameters__

|Field|	Type|	Description|
|-------|-------------------|-------------------------------|
|requestTime|	String|	Order specific identification generated by nidhi|
|orderNo|	String|	Last updated status of the order |

##  Cancel Order

__Request Structure__

```
{
    "userId": "<USER_ID>",
    "orderNo": "20052000000017"
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|The unique, permanent user ID registered with the broker           |
|orderNo|String	|Order Number is defined as Unique number it can be generated while placing the order            |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "requestTime": "17:53:53 22-02-2023",
            "orderNo": "23022200000028"
        }
    ]
}
```
__Parameters__

|Field|	Type|	Description|
|-------|-------------------|-------------------------------|
|requestTime|	String|	|
|orderNo|	String|Order Number is defined as Unique number it can be generated while placing the order |

## OrderMargin

__Request Structure__

```
{
    "userId": "J111",
    "actId": "J111",
    "exchange": "MCX",
    "tradingSymbol": "SILVERMIC",
    "qty": "1",
    "price": "0",
    "product": "M",
    "tranType": "B",
    "prcType": "MKT",
    "triggerPrice":"",
    "bookLossPrice":""
}

```

__Input parameters__


|Field	|           Type	|                    Description|
|-------|-------------------|-------------------------------|
|userId|          String          | The unique, permanent user ID registered with the broker                       |                                   
|actId|           String         | Users Logged in ID will be displayed                      |                                   
|exchange|        String            |  Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)                      |                                  
|tradingSymbol|    String                |Exchange tradingsymbol of the of the instrument                        |                                   
|qty|           String         |Quantity to transact                        |                                 
|price|           String         | Price at which main leg of bracket order will be placed                       |                                 
|product|          String          |Product code (MIS or CNC or NRML)                        |                        
|tranType|          String          |Buy and Sell                        |                           
|prcType|            String        |	Price type(L or MKT or SL or SL-M)                        |                 
|triggerPrice|String|                            |
|bookLossPrice|String|                         |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "remarks": "Insufficient Balance",
            "cash": "0.00",
            "marginUsed": "65205.00",
            "orderMargin": "65205.00",
            "marginUsedPrev": "0.00"
        }
    ]
}

```
__Parameters__

|Field|	Type|	Description|
|-------|-------------------|-------------------------------|
|remarks |	String|	OOrder description/Tag|
|cash |	String|	 |
|marginUsed  |	String|	 |
|orderMargin  |	String|	 |




## Fetch Order Book

__Request Structure__
```
{
    "userId": "<USER_ID>",
    "product": ""
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|  String	|The unique, permanent user ID registered with the broker               |
|product	|String	|Product code (MIS or CNC or NRML)            |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
      {
            "orderNo": "23012000000022",
            "kidId": "1",
            "userId": "SKY100",
            "actId": "SKY100",
            "exch": "NSE",
            "tradingSymbol": "ZOMATO-EQ",
            "qty": "1",
            "orderEntryTime": "20-01-2023 14:30:50",
            "tranType": "B",
            "priceType": "LMT",
            "ret": "DAY",
            "token": "5097",
            "multiplier": "1",
            "priceFactor": "1.000000",
            "pricePrecision": "2",
            "lotSize": "1",
            "tickSize": "0.05",
            "price": "52.00",
            "rPrice": "52.00",
            "avgTradePrice": null,
            "disclosedQty": "0",
            "product": "I",
            "orderStatus": "REJECTED",
            "fillShares": null,
            "exchUpdateTime": null,
            "exchOrderId": null,
            "rQty": "1",
            "formattedInsName": "ZOMATO LIMITED",
            "ltp": null,
            "rejectedReason": "SAF:Yel is down",
            "triggerPrice": null,
            "bookProfitPrice": null,
            "bookLossPrice": null,
            "trailingPrice": null,
            "norenTime": "14:30:50 20-01-2023",
            "mktProtection": null
        }
    ]
}
```
__Parameters__

|Field|	Type|	Description|
|-------|-------------------|-------------------------------|
|orderNo|    String           |Order Number is defined as Unique number it can be generated while placing the order                      |
|kidId |     String         |                      |                             
|userId |     String         | The unique, permanent user ID registered with the broker                     |                             
|actId |       String       | The unique, permanent user ID registered with the broker                     |                                   
|exch |     String         |Exchange (NSE or BSE or NFO or MCX)                      |                                
|tradingSymbol |  String            |Exchange tradingsymbol of the of the instrument                      |                                      
|qty |        String      | Quantity to transact                     |                              
|orderEntryTime |    String          |                      |                                      
|tranType |      String        | Buy and Sell                     |                              
|priceType |     String         |PriceType (Limit , Market , SL , SL-M)                      |                                
|ret |         String     |Retention type (from LoadRetentionType rest api).These orders state the system to keep the orders pending until the market price reaches the specified limit order price. The various retention orders are: Day or End of Session Order: This is the most commonly used retention type                      |                                
|token |     String         | Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details                     |                                
|multiplier |  String            |  The Multiplier Of Scrip                    |                              
|priceFactor |  String           |                      |                                     
|pricePrecision |  String            |                      |                              
|lotSize |      String        |  Quantity of a single lot                    |                              
|tickSize |   String           |   Ticker Size Of The Scrip (in paisa).Tick size is the minimum price change between different bid and offer prices of an asset traded on an exchange platform                   |                                 
|price |       String       | Price at which main leg of bracket order will be placed                     |                                     
|rPrice |     String         |                      |                                 
|avgTradePrice|  String            |                      |                               
|disclosedQty|   String           | Quantity to be disclosed (may be different from actual quantity) to the public exchange orderbook. Only for equitie                     |                              
|product|      String        | Product code (MIS or CNC or NRML)                     |                              
|orderStatus|   String           |                      |                                     
|fillShares|     String         |  The Number of shares got filled                    |                               
|exchUpdateTime|    String          |                      |                                      
|exchOrderId |      String        |                      |          
|rQty |      String        |                      |                                      
|formattedInsName|  String                |                 |
|ltp             |  String                |  Last trade price of the scrip. The price at which the final trade happens between a buyer and a seller               |
|rejectedReason  |  String                |Rejection Reason for the order will be displayed                 |                
|triggerPrice    |  String                |                 |              
|bookProfitPrice |  String                |                 |                 
|bookLossPrice   |   String               |                 |              
|trailingPrice   |   String               |                 |             
|norenTime       |   String               |                 |         
|mktProtection   |     String             | A market-with-protection order cancels an order to buy or sell stock or other assets and re-submits it as a limit order. A broker might submit a market-with-protection order if the price of the stock has moved unexpectedly and dramatically since the market order was placed.                |               


<!-- ##  Order Status

 The status field in the order response shows the current state of the order. The status values are largely self explanatory. The most common statuses are OPEN, COMPLETE, CANCELLED, and REJECTED.

 An order can traverse through several interim and temporary statuses during its lifetime. For example, when an order is first placed or modified, it instantly passes through several stages before reaching its end state. Some of these are highlighted below.



|Status                   |                                                                    |
|-------------------------|--------------------------------------------------------------------|
|PUT ORDER REQ RECEIVED   |Order request has been received by the backend                      |
|VALIDATION PENDING       |Order pending validation by the RMS (Risk Management System)        |
|OPEN PENDING             |Order is pending registration at the exchange                       |
|MODIFY VALIDATION PENDING|Order's modification values are pending validation by the RMS       |
|MODIFY PENDING           |Order's modification values are pending registration at the exchange|              
|TRIGGER PENDING          |Order's placed but the fill is pending based on a trigger price.    |
|CANCEL PENDING           |Order's cancellation request is pending registration at the exchange|
|AMO REQ RECEIVED         |Same as PUT ORDER REQ RECEIVED, but for AMOs                        | -->



##  Fetch Trade Book


__Request Structure__

```
{
    "userId": "<USER_ID>",
    "actId": "<USER_AC>"
}
```
__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|The unique, permanent user ID registered with the broker           |
|actId	|String	| Users Logged in ID will be displayed         |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "orderNo": "23012000000022",
            "userId": "J111",
            "actId": "J111",
            "exchange": "NSE",
            "priceType": "MKT",
            "ret": "DAY",
            "product": "C",
            "fillId": "75989650",
            "fillTime": "03-02-2023 09:55:32",
            "tranType": "B",
            "tradingSymbol": "SITINET-EQ",
            "qty": "1",
            "token": "13998",
            "fillshares": "1",
            "fillqty": "1",
            "pricePrecision": "2",
            "lotSize": "1",
            "tickSize": "0.05",
            "price": "0.00",
            "prcftr": "1.000000",
            "fillprc": "1.50",
            "exchUpdateTime": "03-02-2023 09:55:32",
            "exchOrderId": "1300000005328214",
            "formattedInsName": "SITINET-EQ",
            "ltp": null
        }
    ]
}
```
__parameters__

|Field	|           Type	|                    Description|
|-------|-------------------|-------------------------------|
|orderNo|          String          |                        |                                   
|userId|          String          |The unique, permanent user ID registered with the broker                        |                                   
|actId|           String         | Users Logged in ID will be displayed                       |                                   
|exchange|        String            | Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)                       |                                  
|priceType|  String                | 	Price type(L or MKT or SL or SL-M)                       |                                   
|ret|           String         |  Retention type (from LoadRetentionType rest api).These orders state the system to keep the orders pending until the market price reaches the specified limit order price. The various retention orders are: Day or End of Session Order: This is the most commonly used retention type                      |                                 
|product|           String         | Product code (MIS or CNC or NRML)                       |                                 
|fillId|          String          |  Fill Id                      |                        
|fillTime|          String          | Fill Time                       |                           
|tranType|            String        |  Buy and Sell                      |                  
|tradingSymbol|String|   Exchange tradingsymbol of the of the instrument                         |
|qty|String| Quantity to transact                        |
|token|String|  Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details                       |
|fillshares|String|The Number of shares got filled                         |
|fillqty|String|The Number of shares got filled                         |
|pricePrecision|String|                         |
|lotSize|String| Quantity of a single lot                        |
|price|String| Price at which main leg of bracket order will be placed                        |
|prcftr|String|                        |
|fillprc|String|                         |
|exchUpdateTime|String|                         |
|exchOrderId|String|                         |
|formattedInsName|String|                         |
|ltp|String|  Last trade price of the scrip. The price at which the final trade happens between a buyer and a seller                       |



## Order History

__Request Structure__

```
{
    "userId": "<USER_ID>",
   "orderNo": "23020400000012"
}
```
__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|The unique, permanent user ID registered with the broker           |
|orderNo	|String	| Order Number is defined as Unique number it can be generated while placing the order           |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "orderNo": "23020400000012",
            "userId": "J111",
            "actId": "J111",
            "exchange": "NSE",
            "tradingSymbol": "ZOMATO-EQ",
            "quantity": "1",
            "transType": "B",
            "priceType": "LMT",
            "ret": "DAY",
            "token": "5097",
            "pricePrecision": "2",
            "lotSize": "1",
            "tickSize": "0.05",
            "price": "52.00",
            "avgPrice": null,
            "disclosedQty": null,
            "product": "I",
            "status": "OPEN",
            "report": "AMO received",
            "fillshares": null,
            "time": "20:11:42 04-02-2023",
            "exchTime": null,
            "remarks": null,
            "exchOrderNo": null
        }
    ]
}
```
__parameters__

|Field	|           Type	|                    Description|
|-------|-------------------|-------------------------------|
|orderNo|          String          |  Order Number is defined as Unique number it can be generated while placing the order                      |                                   
|userId|          String          |  The unique, permanent user ID registered with the broker                      |                                   
|actId|           String         |  The unique, permanent user ID registered with the broker                      |                                   
|exchange|        String            |                        |                                  
|tradingSymbol|   String                |  Exchange tradingsymbol of the of the instrument                      |                                   
|quantity|           String         | Quantity to transact                       |                                 
|priceType|           String         | PriceType (Limit , Market , SL , SL-M)                       |                                 
|ret|          String          |  Retention type (from LoadRetentionType rest api).These orders state the system to keep the orders pending until the market price reaches the specified limit order price. The various retention orders are: Day or End of Session Order: This is the most commonly used retention type                      |                        
|token|          String          |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details                        |                           
|pricePrecision|            String        |                        |                  
|lotSize|String|Quantity of a single lot                            |
|tickSize|String|Ticker Size Of The Scrip (in paisa).Tick size is the minimum price change between different bid and offer prices of an asset traded on an exchange platform                         |
|price|String|Price at which main leg of bracket order will be placed                         |
|avgPrice|String|                         |
|disclosedQty|String| Quantity to be disclosed (may be different from actual quantity) to the public exchange orderbook. Only for equitie                        |
|product|String|Product code (MIS or CNC or NRML)                         |
|status|String|                         |
|fillshares|String|The Number of shares got filled                         |
|time|String|                         |
|exchTime|String|                         |
|remarks|String|Order description/Tag                         |
|exchOrderNo|String|                         |




