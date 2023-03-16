---
title: User Settings
---

## Profile

## Preference

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| GET|/mobpreference    |Fetch Preference for Mobile App|
| GET|/webpreference |Get Multiple Index Details with titles|

### Mobile Preference

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
     	"chart":"tradingview",
    	"Poastatus":"0", 
  	    "mstickyorder:"0", 
  	    "mTheme":"0",
        "msingleDepth":"0", 
        "mfixedHeader":"0", 
}

```
__parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|chart	 |String       |Equity Cash        |
|Poastatus	 |String	    |Futures & Options  |
|mstickyorder    |String	    |Currency           |
|msingleDepth      |String    |Cash               |
|mfixedHeader    	 |String	    |Commodity          |


### Web Preference

__Request Structure__ 

```
{

"userID":"<USER_ID>"

}
```
__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|   


__Response Structure__

```
   {
     	 "chart":"tradingview",
    	 "Poastatus":"0", 
  	     "wstickyorder:"0", 
  	     "wTheme":"0",
         "wsingleDepth":"0", 
          "mwatch":"0", 
    }
```
__parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|chart	 |String       |Equity Cash            |
|Poastatus	 |String	    |Futures & Options  |
|wstickyorder    |String	    |Currency       |
|wTheme      |String    |Cash               |
|wsingleDepth    	 |String	    |Commodity  |
|mwatch    	 |String	    |Commodity          |
