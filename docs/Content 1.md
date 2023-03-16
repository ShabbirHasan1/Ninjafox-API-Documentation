---
title: Content 1
---

## Market Watch

The Market Watch services is used to retrieve watchlist of a particular User. All valid instruments can be added to the Market Watch. The count of the Market Watch and total number of scrips per market watch is configurable during the installation of the middleware.

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|marketWatch/createMW|Create marketWatch| 
| Post|marketWatch/getAllMwScrips |Get all Market Watch & scrips from Market Watch.|
| Post|marketWatch/getMWScrips |get market watch scripsrequest.|
| Post|marketWatch/renameMW|Rename Market Watch| 
| Post|marketWatch/sortMwScrip|Sort scrips in Market Watch.| 
| Post|marketWatch/addscrip |Add Scrip to the Market Watch.|
| Post|marketWatch/deletescrip | Delete Scrip from Market Watch.|
| Post|pre-def/mw/get |get predefined market watch| 


### Create MarketWatch

__Request Structure__

```
{
    "userId": "<USER_ID>"
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	| The unique, permanent user ID registered with the broker       |


__Response Structure__

```
{
    "stat": "Ok",
    "message": "Market Watch Created Successfully",
    "result": [
        {
            "mwId": "1",
            "mwName": "MWList1",
            "scrips": null
        },
        {
            "mwId": "2",
            "mwName": "MWList2",
            "scrips": null
        },
        {
            "mwId": "3",
            "mwName": "MWList3",
            "scrips": null
        },
        {
            "mwId": "4",
            "mwName": "MWList4",
            "scrips": null
        },
        {
            "mwId": "5",
            "mwName": "MWList5",
            "scrips": null
        }
    ]
}
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|mwId	 |String       |Unique market watch ID        |
|mwName	 |String	    |Unique market watch Name |
|scrips       |ArrayList	    |List of scripts in market watch   |

###  Get All MarketWatch

__Request Structure__

```
{
    "userId": "<USER_ID>"
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	| The unique, permanent user ID registered with the broker         |



__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "mwId": "1",
            "mwName": "TESTMW2",
            "scrips": [
                {
                    "exchange": "NFO",
                    "segment": "nse_fo",
                    "token": "58298",
                    "tradingSymbol": "NIFTY23FEB23C16100",
                    "expiry": "2023-02-23",
                    "sortOrder": 2,
                    "pdc": "1853.65",
                    "symbol": "NIFTY",
                    "formattedInsName": "NIFTY FEB 16100 CE"
                }
            ]
        },
        {
            "mwId": "2",
            "mwName": "TESTMW2",
            "scrips": null
        }
    ]
}
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|mwId	 |String       |Unique market watch ID        |
|mwName	 |String	    |Unique market watch Name  |
|scrips       |String	    |List of scripts in market watch    |



###  Get MarketWatch 

__Request Structure__

```
{
    "userId": "<USER_ID>"
    "mwId": "1"
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|The unique, permanent user ID registered with the broker        |
|mwId	|String	| Unique market watch ID       |



__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "exchange": "NSE",
            "segment": "nse_cm",
            "token": "16249",
            "tradingSymbol": "INFIBEAM-EQ",
            "expiry": null,
            "sortOrder": 1,
            "pdc": "15.7",
            "symbol": "INFIBEAM",
            "formattedInsName": "INFIBEAM-EQ"
        }
    ]
}
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|exchange	 |String       |Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)        |
|segment	 |String	    |Segment the instrument belongs to |
|token       |String	    |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details          |
|tradingSymbol |String  |Exchange tradingsymbol of the of the instrument|
|expiry    	 |Date	    | Expiry date of the Contract         |
|sOrder   |String	    |  Sorting Order of Market Watch        |
|pdc          |String	    |  previous date closed      |
|symbol     	 |String	    |  |
|formattedInsName  |String   | Formatted Instrument Name |

### Rename MarketWatch

__Request Structure__

```
{
    "userId": "<USER_ID>",
    "mwId": "2",
    "mwName": "TESTMW2"
}
```
__Input parameters__


|Field	| Type	|Description|
|-------|---- --|-----------|
|userId	|String	|The unique, permanent user ID registered with the broker          | 
|mwId	|Int	|Market Watch ID          | 
|mwName	|String	| Unique market watch Name          | 

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": []
}

```

### Sort MarketWatch

__Request Structure__


```
{
    "mwId": "2",
    "mwName": "MWList1",
    "userId": "<USER_ID>",
    "scripData": [
        {
            "exch": "NSE",
            "token": "16249",
            "sOrder": 1
        },
        {
            "exch": "NSE",
            "token": "1594",
            "sOrder": 2
        }
    ]
}
```
__Input parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|mwId	 |String       |Unique market watch ID       |
|mwName	 |String	    |Unique market watch Name  |
|userId       |String	    |The unique, permanent user ID registered with the broker              |
|scripData |String  |List of scripts data               |
|exch    	 |String	    |Exchange (NSE or BSE or NFO or MCX)          |
|token   |String	    |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details          |
|sOrder    	 |String	    |order of script in list          |
|exch    	 |String	    |Exchange (NSE or BSE or NFO or MCX)          |
|token|Strin       |Token of the scrip. Token Number is a unique code given to all companies listed|on the exchange. Selected Instrument token number will be displayed under scrip details
|sOrder    	 |String	    |order of script in list          |

__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": []
}
```




### Add Instrument

__Request Structure__

```
{
    "userId": "<USER_ID>",
    "mwId": "1",
    "scripData": [
        {
            "exch": "NSE",
            "token": "16249"
        }
    ]
}

```
__Input parameters__


|Field	| Type	|Description|
|-------|---- --|-----------|
|userId	|String	|The unique, permanent user ID registered with the broker  |
|mwId	|String	|Unique market watch ID   |
|exch	|String	|Exchange (NSE or BSE or NFO or MCX)    |
|token	|String	|Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details      |


__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "exchange": "NSE",
            "segment": "nse_cm",
            "token": "16249",
            "tSymbol": "INFIBEAM-EQ",
            "expiry": null,
            "sOrder": 3,
            "pdc": "16.2",
            "niceName": "INFIBEAM-EQ"
        }
    ]
}
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|exchange	 |String       |Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)        |
|segment	 |String	    |Segment the instrument belongs to  |
|token       |String	    |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details           |
|tSymbol |Equity  |Exchange tradingsymbol of the of the instrument              |
|expiry    	 |String	    |Expiry date (for derivatives)         |
|sOrder   |Int	    |order of script in list |
|pdc    	 |String	    |Previous day Close  |
|niceName    	 |String	    |Formatted Instrument Name |

### Delete Instrument

__Request Structure__


```
{
    "userId":"<USER_ID>",
    "mwId": "1",
    "scripData": [
        {
            "exch": "NSE",
            "token": "212"
        }
    ]
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|---- --|-----------|
|userId	|String	|The unique, permanent user ID registered with the broker    |
|mwId	|String	|Unique market watch ID  |
|exch	|String	|Exchange (NSE or BSE or NFO or MCX)    |
|token	|String	|Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details      |

__Response Structure__


```
{
    "status": "Ok",
    "message": "Success",
    "result": []
}
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|status	 |String       |       |
|data	 |String	    | |

### Predefined Watch List

__Request Structure__

```
{
    "userId": "<USER_ID>"
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	| The unique, permanent user ID registered with the broker         |


__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "mwId": 1,
            "mwName": "NIFTY 50",
            "position": 1,
            "scrips": [
                {
                    "token": "25",
                    "exchange": "NSE",
                    "segment": "nse_cm",
                    "symbol": "ADANIENT",
                    "tradingSymbol": "ADANIENT-EQ",
                    "formattedInsName": "ADANIENT-EQ",
                    "pdc": "1779.1",
                    "lotSize": "1",
                    "tickSize": "0.05",
                    "sortOrder": 1
                }
              ]
            }
          ]
        }    
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|token	 |Int       |Equity Cash        |
|exchange	 |String	    |Futures & Options  |
|segment       |String	    |Currency           |
|symbol |String  |Cash               |
|tradingSymbol    	 |String	    |Commodity          |
|formattedInsName   |String	    |Commodity          |
|pdc    	 |String	    |Commodity          |
|lotSize    	 |String	    |Commodity          |
|tickSize    	 |String	    |Commodity          |
|sortOrder    	 |Int	    |Commodity          |



## Contract

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|/scrip/search|Get Marketing Response to show in banner| 
| Post|/scrip/contract/info|Get Marketing Response to show in banner| 


### Scrip Search

__Request Structure__

```
{
    "exchange": [
        "ALL"
    ],
    "symbol": "INFY"
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|Exchange	|String	|           |
|symbol  	|String	|           |



__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    {
            "exchange": "NSE",
            "segment": "nse_cm",
            "symbol": "INFY-EQ",
            "token": "1594",
            "formattedInsName": "INFY-EQ",
            "weekTag": "null",
            "companyName": "INFOSYS LIMITED"
        },
}
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|exchange	 |String       |Equity Cash        |
|segment	 |String	    |Futures & Options  |
|symbol       |String	    |Currency           |
|token |String  |Cash               |
|formattedInsName    	 |String	    |Commodity          |
|weekTag   |String	    |Commodity          |
|companyName    	 |String	    |Commodity          |


### ContractInfo

__Request Structure__

```
{
    "token": "212",
    "exch": "nse"
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|token	|String	|           |
|exch  	|String	|           |



__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "isin": "INE208A01029",
            "freezeQty": "227",
            "scrips": [
                {
                    "exchange": "NSE",
                    "token": "212",
                    "tradingSymbol": "ASHOKLEY-EQ",
                    "lotSize": "1",
                    "tickSize": "0.05",
                    "symbol": "ASHOKLEY",
                    "formattedInsName": "ASHOKLEY-EQ",
                    "pdc": "149.45",
                    "insType": "0"
                }
            ]
        }
    ]
}
```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|exchange	 |String       |Equity Cash        |
|token	 |String	    |Futures & Options  |
|tradingSymbol       |String	    |Currency           |
|lotSize |String  |Cash               |
|tickSize    	 |String	    |Commodity          |
|symbol   |String	    |Commodity          |
|formattedInsName    	 |String	    |Commodity          |
|pdc    	 |String	    |Commodity          |
|insType    	 |String	    |Commodity          |


### Contract Master

## Equity Content

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| GET|/eqsectors  |Get Sector details with 3M, 6M and 1 Year return| 

### Sector

__Response Structure__

```
{
  "stat": "ok",
  "message": "if(stat is ok) ? return 'success' : 'fail message'",
  "result": [
    {
      "sectorName": "METAL",
      "imageUrl": "https://image-utl",
      "3M": "+10.46%",
      "6M": "+10.46%",
      "1Y": "+10.46%",
    },
    {
      "sectorName": "IT",
      "imageUrl": "https://image-utl",
      "3M": "+10.46%",
      "6M": "+10.46%",
      "1Y": "+10.46%",
    },
```

### Screeners
  

