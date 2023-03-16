---
title: Content 2
---



<!-- | GET|/eqsectorsall |Get Multiple Stock Details along with its sectors in headings| 
| GET|/heatmap     |Get Multiple Future Segment with 1D return %|
| GET|/futsectorsall |Get future breakup along with 1D return %|
| GET|/etf            |Get ETF details along with its |
| GET|/eqscan         |Limited tabs with only 5 responses|
| GET|/eqscanall      |All tabs with full response| 
| GET|/futscan         |Limited tabs with only 5 responses|
|GET |/futscanall|All tabs with full response.|
|GET|/appversion|To check app version check. | -->

## F&O Content

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|/restpy/get_strike_data|Get Marketing Response to show in banner| 
| GET|/indices    |Fetch Index Details|
| GET|/futures    |Fetch 5 Future Details|
| GET|/futuresall |Get Multiple Future Details with titles| 

### Option Chain


__Request Structure__

```
{
    "underlying": "BANKNIFTY",
    "expiry": "16FEB23",
    "interval": 10
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-----------------------|
|underlying	|String	|           |
|expiry  	|String	|           |
|interval  	|String	|           |




__Response Structure__

```
{
    "CE": {
        "ltp": "1123.85",
        "forInsName": "BANKNIFTY 16FEB 40600 CE",
        "gVal": "0.04934980966015927",
        "oi": "18700",
        "pdoi": "18700.0",
        "pdc": "1123.85",
        "token": "43635"
    },
    "PE": {
        "ltp": "6.4",
        "forInsName": "BANKNIFTY 16FEB 40600 PE",
        "gVal": "2.1375184935922014",
        "oi": "752725",
        "pdoi": "752725",
        "pdc": "6.4",
        "token": "43636"
    },
    "strikeprice": "40600"
},
{
    "CE": {
        "ltp": "1018.0",
        "forInsName": "BANKNIFTY 16FEB 40700 CE",
        "gVal": "0.09361949185530213",
        "oi": "35475",
        "pdoi": "35475.0",
        "pdc": "1018.0",
        "token": "43637"
    },
    "PE": {
        "ltp": "7.1",
        "forInsName": "BANKNIFTY 16FEB 40700 PE",
        "gVal": "2.235488387017995",
        "oi": "787225",
        "pdoi": "787225",
        "pdc": "7.1",
        "token": "43639"
    },
    "strikeprice": "40700"
}

```
__Parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|ltp	 |String       |Last available NAV price of the fund       |
|forInsName	 |String	    | |
|gVal       |String	    |           |
|oi |String  |The Open Interest for a futures or options contract ?               |
|pdoi    	 |String	    |          |
|pdc   |String	    |Previce Day Close Value          |
|token    	 |String	    |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details          |
 
### FNO Screeners

### Indices

__Request Structure__ 
```
{

"userID":"<USER_ID>"

}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	| The unique, permanent user ID registered with the broker|  

__Response Structure__


```
{
    "status": "SUCCESS",
    "message": null,
    "result": [
        {
            "scripName": "NIFTY 50",
            "sortOrder": 0,
            "exchange": "NSE",
            "nextExpiry": "2022-11-24",
            "token": "26000",
            "pdc": "",
        },
             {
            "scripName": "NIFTY BANK",
            "sortOrder": 1,
            "exchange": "NSE",
            "nextExpiry": "2022-11-24",
            "token": "26009",
            "pdc": "",
        },
             {
            "scripName": "NIFTY FIN SERVICE",
            "sortOrder": 1,
            "exchange": "NSE",
            "nextExpiry": "2022-11-24",
            "token": "26037",
            "pdc": "",
        }
    ]
}
```

__parameters__

|Field	     |Type   	|description        |
|------------|----------|------------------ |
|scripName	 |String       |The Name of script        |
|sortOrder	 |Int	    |  |order of script in list
|exchange    |String	    | Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)          |
|nextExpiry  |String    |               |
|token    	 |String	    | Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details         |
|pdc         |String	    |Previce Day Close Value          |


<!-- ## Indicesall

__Request Structure__

```
{
"userID:"<USER_ID>"
}

```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|    -->


### Futures 

__Request Structure__ 

```
{
"userID:"<USER_ID>"
}
```

__Input parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	| The unique, permanent user ID registered with the broker|  

__Response Structure__

```
{
    "status": "SUCCESS",
    "message": null,
    "result": [
        {
            "scripName": "NIFTY DEC FUT",
            "sortOrder": 0,
            "exchange": "NFO",
            "nextExpiry": "2022-11-24",
            "token": "26000",
            "pdc": "",
        },
             {
            "scripName": "BANKNIFTY DEC FUT",
            "sortOrder": 1,
            "exchange": "NFO",
            "nextExpiry": "2022-11-24",
            "token": "26009",
            "pdc": "",
        },
             {
            "scripName": "FINNIFTY DEC FUT",
            "sortOrder": 1,
            "exchange": "NFO",
            "expiry": "2022-11-24",
            "token": "26037",
            "pdc": "",
        }
    ]
}
```
__parameters__

|Field	     |Type   	|description        |
|------------|----------|------------------ |
|scripName	 |String       |The Name of script        |
|sortOrder	 |Int	    |order of script in list  |
|exchange    |String	    |Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)           |
|expiry      |String    |Expiry date (for derivatives)               |
|token    	 |String	    |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details          |
|pdc         |String	    |Previce Day Close Value          |


### Detailed Future 

__Request Structure__ 

```
{
"userID:"<USER_ID>"
}
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|   

__Response Structure__

```
{
    "status": "SUCCESS",
    "message": null,
    "result": [
        {
            "listId": 1,
            "listName": "NIFTY FUTURES",
            "scrips": [
                {
                    "scripName": "NIFTY22NOVFUT",
                    "sortOrder": 0,
                    "exchange": "NFO",
                    "expiry": "2022-11-24",
                    "token": "53395",
                    "pdc": "17688.65",
                    "symbol": "NIFTY22NOVFUT"
                },
                {
                    "scripName": "BANKNIFTYNOVFUT",
                    "sortOrder": 0,
                    "exchange": "NFO",
                    "expiry": "2022-11-24",
                    "token": "53394",
                    "pdc": "17688.65",
                    "symbol": "NIFTY22NOVFUT"
                }
            ]
        },
        {
            "listId": 2,
            "listName": "BANK NIFTY FUTURES",
            "scrips": [
                {
                    "scripName": "BANKNIFTYNOVFUT",
                    "sortOrder": 1,
                    "exchange": "NFO",
                    "expiry": "2022-11-24",
                    "token": "53394",
                    "pdc": "17688.65",
                    "symbol": "NIFTY22NOVFUT"
                },
                {
                    "scripName": "NIFTY22NOVFUT",
                    "sortOrder": 0,
                    "exchange": "NFO",
                    "expiry": "2022-11-24",
                    "token": "32456",
                    "pdc": "17688.65",
                    "symbol": "NIFTY22NOVFUT"
                }
            ]
        }
    ]
}
```

__parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|scripName	 |String       |The Name of script        |
|sortOrder	 |Int	    |order of script in list  |
|exchange    |String	    |Name of the exchange (NSE, BSE, NFO, CDS, BCD, MCX)           |
|expiry      |String    |Expiry date (for derivatives)               |
|token    	 |String	    |Token of the scrip. Token Number is a unique code given to all companies listed on the exchange. Selected Instrument token number will be displayed under scrip details          |
|pdc         |String	    |Previce Day Close Value          |
|symbol|String | Exchange symbol of the of the instrument|







## Mobile DashBoard

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| GET| dashboard/investment   |Get investing dashboard|
| GET| dashboard/trading  |Get trading dashboard|


### Investing

  
__Request Structure__ 

  No Body

__Response Structure__
 
```
  {
    "status": "Ok",
    "message": "Success",
    "preferences": {
        "mCard": "M",
        "indices": "T",
        "scanners": "T",
        "cards": "F",
        "topSector": "T",
        "funds": "T",
        "holdings": "T"
    },
    "indicesData": [
        {
            "scripName": "NIFTY 50",
            "sortOrder": 0,
            "exchange": "NSE",
            "expiry": null,
            "token": "26000",
            "pdc": "0",
            "symbol": "NIFTY 50 INDEX"
        }
    ],
    "topSectorData": [
        {
            "sectorName": "BANKING",
            "imageUrl": "https://image-utl",
            "threeMonths": "+10.46% ",
            "sixMonths": "+10.46% ",
            "oneYear": "+10.46% "
        }
    ],
    "mcardData": [
        {
            "title": "Social Strategy",
            "subTitle": "Balanced diversified portfolios",
            "imageUrl": "https://image-utl",
            "cardValue": "+10.46%",
            "buttonName": "Know More",
            "buttonUrl": "https://know_more",
            "inApp": "true",
            "cardColor": "FFF8E5",
            "buttonColor": "FFF8E5"
        } 
    ]
}

```
__parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|preferences  	 |String       |Equity Cash        |
|indicesData   	 |List	    |Futures & Options  |
|topSectorData     |List	    |Currency           |
|mcardData        |List    |Cash               |


### Trading
  
__Request Structure__ 

  No Body  

__Response Structure__ 

```
{
    "status": "Ok",
    "message": "Success",
    "preference": [
        {
            "key": "positions",
            "show": "T",
            "isEnabled": "T",
            "sortOrder": "1"
        }
    ],
    "futuresData": [],
    "fnoScannersData": [],
    "heatMapData": [
        {
            "sectorId": 1,
            "sectorName": "METAL",
            "oneDay": "+10.46"
        }
    ]
}
```

__parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|preferences  	 |String       |Equity Cash        |
|futuresData   	 |String	    |Futures & Options  |
|fnoScannersData      |String	    |Currency           |
|heatMapData       |String    |Cash               |

## Charts

### Intraday Charts

### History


## Corporate Action

## Marketing

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| GET|/marketing  |Get Marketing Response to show in banner| 


__Request Structure__ 

```
{
"userID:"<USER_ID>"
}
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|   

__Response Structure__

```
{
  "stat": "ok",
  "message": "if(stat is ok) ? return 'success' : 'fail message'",
  "result": [
    {
      "title": "Social Strategy",
      "subTitle": "Balanced diversified portfolios",
      "imageUrl": "https://image-utl",
      "cardValue": "+10.46%",
      "buttonName": "Know More",
      "buttonUrl": "https://know_more",
      "inApp": true, // if(true) open in app via webview else open in Browser
      "cardColor": "FFF8E5"
     "buttonColor": "FFF8E5" 
    },
    {
      "title": "Social Strategy",
      "subTitle": "Balanced diversified portfolios",
      "imageUrl": "https://image-utl",
      "cardValue": "+10.46%",
      "buttonName": "Know More",
      "buttonUrl": "https://know_more",
      "inApp": true, // if(true) open in app via webview else open in Browser
      "cardColor": "FFF8E5"
     "buttonColor": "FFF8E5" 
    },
    {
      "title": "Social Strategy",
      "subTitle": "Balanced diversified portfolios",
      "imageUrl": "https://image-utl",
      "cardValue": "+10.46%",
      "buttonName": "Know More",
      "buttonUrl": "https://know_more",
      "inApp": true, // if(true) open in app via webview else open in Browser
      "cardColor": "FFF8E5"
     "buttonColor": "FFF8E5" 
    }
  ]
}

```

__parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|title	 |String       |Equity Cash        |
|subTitle	 |String	    |Futures & Options  |
|imageUrl    |String	    |Currency           |
|cardValue      |String    |Cash               |
|buttonName    	 |String	    |Commodity          |
|buttonUrl         |String	    |Commodity          |
|inApp      |String	    |Commodity          |
|cardColor      |String	    |Commodity          |
|buttonColor      |String	    |Commodity          |



