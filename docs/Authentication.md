---

title: Authentication

---

The authentication mechanism is handled by customising one of the most reliable open source IAM (Identity & Access Management) in the planet. The authentication layer takes care of integration with RMS/OMS, Mutual Funds and other backend systems.

## Login
### Check Device Info
### Login

|Method	     |APIS  	|Detail        |
|------------|----------|------------------ |
| Post|auth/login  |login|


__Request Structure__ 

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
|userId	|String	|The unique, permanent user ID registered with the broker   |
|password	|String	|The unique,  user Created a Password   |
|source	|String	| Request source from which platform eg., 'MOBILEAPI' or 'RESTAPI'  |



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
|accessToken	|String	|The authentication token that's used with every subsequent request Unless this is invalidated using the API, or invalidated by a master-logout from the Kite Web trading terminal, it'll expire at 6 AM on the next day (regulatory requirement)     |
|tokenType	|String	|Token type i.e, 'Bearer' |
|refreshToken	|String	|A token for getting long standing read permissions. This is only available to certain approved platforms |

 
### Logout
### 2FA Login

## Credentials

### Forget Password

__Request Structure__ 

```
{
    "mobileNo": "1234567890",
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

### Change Password

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

### New Password

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

## OTP


|Method	     |APIS  	|Detail        |
|------------|----------|------------------ |
| Post|access/otp/send  |Send OTP|
| Post|access/otp/validate  |Validate OTP|



### Send OTP

__Request Structure__ 

```
{
    "userId": "1234567890",
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
    "userId": "1234567890",
    "source":"WEB",
    "otp":"353324"
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


|Method	     |APIS  	|Detail        |
|------------|----------|------------------ |
| Post|preferences/get  |Get preferences |
| Post|preferences/update  |Set preferences |


### Get User Preference

__Request Structure__ 

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
|keyVariable	|String	| Preference key Variable  |



__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": [
        {
            "id": 75,
            "keyVariable": "marketWatch",
            "value": "MyList",
            "source": "MOB"
        }
    ]
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|Unique ID     |
|keyVariable	|String	|Preference key Variable |
|value	|String	|Preference key Value |
|source	|String	|Request source from which platform eg., 'MOBILEAPI' or 'RESTAPI' |


### Set User Preference

__Request Structure__ 

```
{
    "userId": "<USER_ID>",
    "source": "MOB",
    "preferences": [
        {
            "id": 10,
            "keyVariable": "marketWatch",
            "value": "PreDefined"
        }
    ]
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|Unique ID   |
|keyVariable	|String	|Preference key Variable   |
|value	|String	| Preference key Value  |



__Response Structure__

```
{
    "status": "Ok",
    "message": "Success",
    "result": null
}  

```


## Update
### Update User Info
