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
        "mfixedHeader":"0" 
}

```
__parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|chart	 |String       |The name of Chart platform        |
|Poastatus	 |String	    |A power of attorney status  |
|mstickyorder    |String	    |Mobile Sticky order flag           |
|msingleDepth      |String    |Mobile Single Depth flag               |
|mfixedHeader    	 |String	    |Mobile Fixed Header flag          |


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
          "mwatch":"0"
    }
```
__parameters__


|Field	     |Type   	|description        |
|------------|----------|------------------ |
|chart	 |String       |The name of Chart platform           |
|Poastatus	 |String	    |A power of attorney status  |
|wstickyorder    |String	    |Mobile Sticky order flag       |
|wTheme      |String    |Web theme Flag               |
|wsingleDepth    	 |String	    |Web single depth flag  |
|mwatch    	 |String	    |market watch flag          |
