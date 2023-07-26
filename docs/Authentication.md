---

title: Authentication

---

# Authentication
The authentication mechanism is handled by customising one of the most reliable open source IAM (Identity & Access Management) in the planet. The authentication layer takes care of integration with RMS/OMS, Mutual Funds and other backend systems.

## Login

|Method	     |APIS  	|Detail        |
|------------|----------|------ ------ |
| Post|access/client/verify  |  |
| Post|access/pwd/validate|    |


### Client Verify

__Request Structure__   

```

{
    "userId": "7904683175"
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|The unique, permanent user ID registered with the broker   |




__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "isExist": "Yes",
            "ucc": "SKY100"
        }
    ]
}
```

__parameters__


<!-- |Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|accessToken	|String	|The authentication token that's used with every subsequent request Unless this is invalidated using the API, or invalidated by a master-logout from the Kite Web trading terminal, it'll expire at 6 AM on the next day (regulatory requirement)     |
|tokenType	|String	|Token type i.e, 'Bearer' |
|refreshToken	|String	|A token for getting long standing read permissions. This is only available to certain approved platforms | -->

|Field	| Type	|Description|
|-------|-------|--------------------|
|isExist	|String	|  |
|ucc	|String	|  |

 
### PassValidation

__Request Structure__ 

```
{
    "userId": "SKY100",
    "source":"WEB",
    "password":"abc@123"
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|  |
|source	|String	| Request source from which platform eg., 'MOBILEAPI' or 'RESTAPI'  |
|password	|String	|  |



__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "totpAvailable": true,
            "token": "JQYARHUURJKI8LGTJCC8DB3AWWEDW30G6WHL8PFIJ34CZGJKT9AH2MIRXCMRZFHWR5MRK8KIV0K7LZUNIW0WGE7SXPUTSVQ6ZGMHMBGTHWGP8OZGHQL1CFBW27WU4MVOTZBLBUJ64X6X2UZ77CBI1ZXTE61UNA353Y382HT74AV4S6D31Q90CM25XX8UY1FGDX3ONVFM4GFP5BO0UB3I20353V2GPOTY84T0C9QUY4QFUP6CQT8SP7128WFM6BKT",
            "kcRole": "ACTIVE_USER"
        }
    ]
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|totpAvailable	|String	|     |
|token	|String	| |
|kcRole	|String	| |


## Credentials

|Method	     |APIS  	|Detail        |
|------------|----------|------ ------ |
| Post|access/pwd/forget | |
| Post|access/pwd/reset | |


### Forget Password

__Request Structure__ 

```
{
    "mobileNo": "<USER_ID>",
    "source":"WEB",
    "pan":"<pan_no>"
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|mobileNo	|String	|Account holder Mobile number will be displayed   |
|source	|String	| Request source from which platform eg., 'MOBILEAPI' or 'RESTAPI'  |
|pan	|String	|Account holder PAN number will be displayed   |



__Response Structure__

```
{
    "status": "Ok",
    "message": "OTP sent to registered mobile No.",
    "result": []
}
```

<!-- __parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|accessToken	|String	|     |
|tokenType	|String	| |
|refreshToken	|String	| | -->

<!-- ### Change Password -->

<!-- __Request Structure__ 

```
{
   "userId":"<USER_ID>",
   "password":"Password",
   "source":"MOB"
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|   |
|password	|String	|   |
|source	|String	|   |



__Response Structure__

```
{
   "status":"Ok",
   "message":"Success",
   "result":[
         {
             "accessToken":"XXXX",
              "tokenType":"Bearer",
              "refreshToken":"XXXX""       
      }
   ]
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|accessToken	|String	|     |
|tokenType	|String	| |
|refreshToken	|String	| | -->

<!-- ### New Password -->

<!-- __Request Structure__ 

```
{
   "userId":"<USER_ID>",
   "password":"Password",
   "source":"MOB"
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|   |
|password	|String	|   |
|source	|String	|   |



__Response Structure__

```
{
   "status":"Ok",
   "message":"Success",
   "result":[
         {
             "accessToken":"XXXX",
              "tokenType":"Bearer",
              "refreshToken":"XXXX""       
      }
   ]
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|accessToken	|String	|     |
|tokenType	|String	| |
|refreshToken	|String	| | -->

### Set Password

__Request Structure__ 

```
{
   "userId":"<USER_ID>",
   "password":"Password",
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|   |
|password	|String	|   |



__Response Structure__

```
{
    "status": "Ok",
    "message": "Password changed sucessfully",
    "result": []
}
```
<!-- 
__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|accessToken	|String	|     |
|tokenType	|String	| |
|refreshToken	|String	| | -->

## OTP


|Method	     |APIS  	|Detail        |
|------------|----------|------------------ |
| Post|access/otp/send  |Send OTP|
| Post|access/otp/validate  |Validate OTP|



### Send OTP

__Request Structure__ 

```
{
    "userId": "<USER_ID>",
    "source":"WEB"
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|The unique, permanent user ID registered with the broker   |
|source	|String	|Request source from which platform eg., 'MOBILEAPI' or 'RESTAPI'   |



__Response Structure__

```
{
    "status": "Ok",
    "message": "OTP sent to registered mobile No.",
    "result": []
}
```

__parameters__

<!-- 
|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|accessToken	|String	|     |
|tokenType	|String	| |
|refreshToken	|String	| | -->


### Validate OTP

__Request Structure__ 

```
{
    "userId": "<USER_Id>",
    "source":"WEB",
    "otp":"1234"
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|userId	|String	|The unique, permanent user ID registered with the broker   |
|source	|String	|Request source from which platform eg., 'MOBILEAPI' or 'RESTAPI'   |
|otp	|String	|One Time Password   |



__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "accessToken": xxxx,
            "refreshToken": xxxx,
            "kcRole": "ACTIVE_USER"
        }
    ]
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|accessToken	|String	|The authentication token that's used with every subsequent request Unless this is invalidated using the API, or invalidated by a master-logout from the Kite Web trading terminal, it'll expire at 6 AM on the next day (regulatory requirement)     |
|tokenType	|String	|Token type i.e, 'Bearer' |
|refreshToken	|String	|A token for getting long standing read permissions. This is only available to certain approved platforms |

## User Preference

|Method	     |APIS  	|Detail             |
|------------|----------|------------------ |
| GET |preferences/web  |Get preferences    |
| Post|preferences/web/update  |Update preferences |


### Get User Preference

<!-- __Request Structure__ 

```
{
    "source" : "MOB",
    "keyVariable" : ""
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|source	|String	|Request source from which platform eg., 'MOBILEAPI' or 'RESTAPI'   |
|keyVariable	|String	| Preference key Variable  | -->



__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "tag": "marketWatch",
            "value": "My Watchlist"
        },
        {
            "tag": "watchListSwitch",
            "value": "Left"
        }
    ]
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|tag	|String	|Unique ID     |
|value	|String	|Preference key Value |


### Update User Preference

 __Request Structure__ 

```
{
    "tag": "orderWindowType",
    "value": "horz"
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|tag	|String	|  |
|value	|String	| Preference key Value  |



__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "tag": "marketWatch",
            "value": "My Watchlist"
        },
        {
            "tag": "watchListSwitch",
            "value": "Left"
        }
    ]
}

``` 
__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|tag	|String	|Unique ID     |
|value	|String	|Preference key Value |

