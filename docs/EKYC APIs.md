---
title: EKYC APIs
---

## Mobile Number 

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|user/sendSmsOtp  |Fetch Index Details|
| Post|user/verifySmsOtp |Get Multiple Index Details with titles|

### Input Mobile

__Request Structure__ 

```
{
    "mobileNo":1234567890
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|mobileNo	|String	|   

__Response Structure__

```
{
   "stat":1,
   "page":null,
   "message":"Success",
   "reason":null,
   "result":{
      "id":6,
      "userName":null,
      "firstName":null,
      "middleName":null,
      "lastName":null,
      "mobileNo":6383817813,
      "emailId":null,
      "emailVerified":0,
      "smsVerified":0,
      "panNumber":null,
      "dob":null,
      "stage":0.0,
      "status":null
   },
   "address_response":null
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|userName	|String	| |
|firstName	|String	| |
|middleName	|String	| |
|lastName	|String	| |
|mobileNo	|String	| |
|emailId	|String	| |
|emailVerified	|String	| |
|smsVerified	|String	| |
|panNumber	|String	| |
|dob	|String	| |
|stage	|String	| |
|status	|String	| |



### Verify Mobile 


__Request Structure__ 

```
{
    "mobileNo":"1234567890",
     "smsOtp":"7765"
}
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|mobileNo	|String	|   |
|smsOtp	|String	|   |


__Response Structure__

```
{
   "stat":1,
   "page":"1",
   "message":"Success",
   "reason":null,
   "result":{
      "id":6,
      "userName":null,
      "firstName":null,
      "middleName":null,
      "lastName":null,
      "mobileNo":6383817813,
      "emailId":"sivaselvan@codifi.in",
      "emailVerified":0,
      "smsVerified":1,
      "panNumber":null,
      "dob":null,
      "stage":0.0,
      "status":null
   },
   "address_response":null
}
```

__parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|userName	|String	| |
|firstName	|String	| |
|middleName	|String	| |
|lastName	|String	| |
|mobileNo	|String	| |
|emailId	|String	| |
|emailVerified	|String	| |
|smsVerified	|String	| |
|panNumber	|String	| |
|dob	|String	| |
|stage	|String	| |
|status	|String	| |

## Email ID

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|user/verifyEmailOtp  |Fetch Index Details|
| Post|user/sendMailOtp |Get Multiple Index Details with titles|

### Input Email

__Request Structure__ 

```
{
    "email":johndoe@gmail.com
}
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|email	|String	|   |

__Response Structure__

```
{
   "stat":1,
   "page":"1",
   "message":"Success",
   "reason":null,
   "result":{
      "id":6,
      "userName":null,
      "firstName":null,
      "middleName":null,
      "lastName":null,
      "mobileNo":6383817813,
      "emailId":"sivaselvan@codifi.in",
      "emailVerified":0,
      "smsVerified":1,
      "panNumber":null,
      "dob":null,
      "stage":0.0,
      "status":null
   },
   "address_response":null
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|userName	|String	| |
|firstName	|String	| |
|middleName	|String	| |
|lastName	|String	| |
|mobileNo	|String	| |
|emailId	|String	| |
|emailVerified	|String	| |
|smsVerified	|String	| |
|panNumber	|String	| |
|dob	|String	| |
|stage	|String	| |
|status	|String	| |


### Verify Email

__Request Structure__ 

```
{
    "id": 12,
    "email": "johndoe@gmail.com"
}
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|   |
|email	|String	|   |


__Response Structure__

```
{
   "stat":1,
   "page":"2",
   "message":"Success",
   "reason":null,
   "result":{
      "id":6,
      "userName":null,
      "firstName":null,
      "middleName":null,
      "lastName":null,
      "mobileNo":6383817813,
      "emailId":"sivaselvan@codifi.in",
      "emailVerified":1,
      "smsVerified":1,
      "panNumber":null,
      "dob":null,
      "stage":1.0,
      "status":"In-Progress"
   },
   "address_response":null
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|userName	|String	| |
|firstName	|String	| |
|middleName	|String	| |
|lastName	|String	| |
|mobileNo	|String	| |
|emailId	|String	| |
|emailVerified	|String	| |
|smsVerified	|String	| |
|panNumber	|String	| |
|dob	|String	| |
|stage	|String	| |
|status	|String	| |

## PAN Card Validation 

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|pan/getPan  |Fetch Index Details|
| Post|pan/saveDOB |Get Multiple Index Details with titles|

### NSDL Validation

__Request Structure__ 

```
{
    "id": 12,
    "panNumber": "ABCDE8123P"
}
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|   
|panNumber	|String	|   


__Response Structure__

```
{
   "stat":1,
   "page":"2.1",
   "message":"Success",
   "reason":null,
   "result":{
      "id":6,
      "userName":"RAMAN  SIVASELVAN",
      "firstName":"RAMAN",
      "middleName":"",
      "lastName":"SIVASELVAN",
      "mobileNo":6383817813,
      "emailId":"sivaselvan@codifi.in",
      "emailVerified":1,
      "smsVerified":1,
      "panNumber":"PDSPS2031F",
      "dob":null,
      "stage":2.1,
      "status":"In-Progress"
   },
   "address_response":null
}

```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|userName	|String	| |
|firstName	|String	| |
|middleName	|String	| |
|lastName	|String	| |
|mobileNo	|String	| |
|emailId	|String	| |
|emailVerified	|String	| |
|smsVerified	|String	| |
|panNumber	|String	| |
|dob	|String	| |
|stage	|String	| |
|status	|String	| |

### KRA Check
 
__Request Structure__ 

```
{
    "id": 6,
    "dob": "23-07-1999"
}
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|   
|dob	|String	|   



__Response Structure__

```
{
   "stat":1,
   "page":"3",
   "message":"Success",
   "reason":null,
   "result":{
      "id":6,
      "userName":"RAMAN  SIVASELVAN",
      "firstName":"RAMAN",
      "middleName":"",
      "lastName":"SIVASELVAN",
      "mobileNo":1234567890,
      "emailId":"sivaselvan@codifi.in",
      "emailVerified":1,
      "smsVerified":1,
      "panNumber":"PDSPS2031F",
      "dob":"20-06-2001",
      "stage":2.2,
      "status":"In-Progress"
   },
   "address_response":null
}
```

__parameters__

|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|userName	|String	| |
|firstName	|String	| |
|middleName	|String	| |
|lastName	|String	| |
|mobileNo	|String	| |
|emailId	|String	| |
|emailVerified	|String	| |
|smsVerified	|String	| |
|panNumber	|String	| |
|dob	|String	| |
|stage	|String	| |
|status	|String	| | 

## Profile 

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|profile/getProfile/?:applicationId |Fetch Index Details|
| Post|profile/saveProfile |Get Multiple Index Details with titles|


###  Get profile 

__Request Structure__ 

```
applicationId=6
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	|   

__Response Structure__

```
{
   "stat":1,
   "page":"4",
   "message":"Success",
   "reason":null,
   "result":{
      "id":4,
      "applicationId":6,
      "fatherName":"RAMAN",
      "applicantName":null,
      "motherName":"MOHANA",
      "occupation":"Private Sector",
      "gender":"Male",
      "title":null,
      "annualIncome":"0-1 lakh",
      "maritalStatus":"Single",
      "politicalExposure":"",
      "tradingExperience":"0-1 year",
      "legalAction":"No"
   },
   "address_response":null
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|applicationId	|String	| |
|fatherName	|String	| |
|applicantName	|String	| |
|motherName	|String	| |
|occupation	|String	| |
|gender	|String	| |
|title	|String	| |
|annualIncome	|String	| |
|maritalStatus	|String	| |
|politicalExposure	|String	| |
|tradingExperience	|String	| |
|legalAction	|String	| |


### Save profile

__Request Structure__ 

```
{
   "applicationId":6,
   "fatherName":"RAMAN",
   "motherName":"MOHANA",
   "occupation":"Private Sector",
   "gender":"Male",
   "annualIncome":"0-1 lakh",
   "maritalStatus":"Single",
   "politicalExposure":"",
   "tradingExperience":"0-1 year",
   "legalAction":"No"
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	| |
|fatherName	|String	| |
|motherName	|String	| |
|occupation	|String	| |
|gender	|String	| |
|annualIncome	|String	| |
|maritalStatus	|String	| |
|politicalExposure	|String	| |
|tradingExperience	|String	| |
|legalAction	|String	| |


__Response Structure__

```
{
   "stat":1,
   "page":"5",
   "message":"Success",
   "reason":null,
   "result":{
      "id":4,
      "applicationId":6,
      "fatherName":"RAMAN",
      "applicantName":null,
      "motherName":"MOHANA",
      "occupation":"Private Sector",
      "gender":"Male",
      "title":null,
      "annualIncome":"0-1 lakh",
      "maritalStatus":"Single",
      "politicalExposure":"",
      "tradingExperience":"0-1 year",
      "legalAction":"No"
   },
   "address_response":null
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|applicationId	|String	| |
|fatherName	|String	| |
|applicantName	|String	| |
|motherName	|String	| |
|occupation	|String	| |
|gender	|String	| |
|title	|String	| |
|annualIncome	|String	| |
|maritalStatus	|String	| |
|politicalExposure	|String	| |
|tradingExperience	|String	| |
|legalAction	|String	| |

## Get UserDetails

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|user/getUsrDetails/?:applicationId  |Fetch Index Details|


__Request Structure__ 

```
applicationId

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	|   

__Response Structure__

```
{
   "stat":1,
   "page":"4.0",
   "message":"Success",
   "reason":null,
   "result":{
      "id":6,
      "userName":"RAMAN  SIVASELVAN",
      "firstName":"RAMAN",
      "middleName":"",
      "lastName":"SIVASELVAN",
      "mobileNo":6383817813,
      "emailId":"sivaselvan@codifi.in",
      "emailVerified":1,
      "smsVerified":1,
      "panNumber":"PDSPS2031F",
      "dob":"20-06-2001",
      "stage":3.0,
      "status":"In-Progress"
   },
   "address_response":{
      "id":3,
      "isdigi":1,
      "accessToken":"a35c408c07ca32e73bcae6e2955322817cd577f1",
      "co":"S/O: Raman",
      "applicationId":6,
      "flatNo":"6/61",
      "address1":"Mulanur",
      "address2":null,
      "landmark":null,
      "street":"ARIVOZHI NAGAR",
      "district":"Tiruppur",
      "state":"Tamil Nadu",
      "country":"India",
      "pincode":638106,
      "isKra":0,
      "kraAddress1":null,
      "kraAddress2":null,
      "kraAddress3":null,
      "kraPin":0,
      "kraCity":null,
      "kraState":null,
      "kraPerAddress1":null,
      "kraPerAddress2":null,
      "kraPerAddress3":null,
      "kraPerPin":0,
      "kraPerCity":null,
      "kraPerState":null
   }
}
```

__parameters__



|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|userName	|String	| |
|firstName	|String	| |
|middleName	|String	| |
|lastName	|String	| |
|mobileNo	|String	| |
|emailId	|String	| |
|emailVerified	|String	| |
|smsVerified	|String	| |
|panNumber	|String	| |
|dob	|String	| |
|stage	|String	| |
|status	|String	| |
|id	|String	|     |
|isdigi	|String	| |
|accessToken	|String	| |
|co	|String	| |
|applicationId	|Int	| |
|flatNo	|String	| |
|address1	|String	| |
|address2	|String	| |
|landmark	|String	| |
|street	|String	| |
|district	|String	| |
|stage	|String	| |
|country	|String	| |
|pincode	|String	| |
|isKra	|String	| |
|stage	|String	| |
|status	|String	| |
|id	|String	|     |
|isdigi	|String	| |
|kraAddress1	|String	| |
|kraAddress2	|String	| |
|kraAddress3	|String	| |
|kraPin	|String	| |
|kraCity	|String	| |
|kraState	|String	| |
|kraPerAddress1	|String	| |
|kraPerAddress2	|String	| |
|kraPerAddress3	|String	| |
|kraPerPin	|String	| |
|kraPerCity	|String	| |
|kraPerState	|String	| |


## Bank Details

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|bank/getBank/?:applicationId|Fetch Index Details|
| Post|bank/getBankAdd|Get Multiple Index Details with titles|
| Post|bank/saveBank |Fetch Index Details|



### Get bank details

__Request Structure__ 

```
applicationId

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	|   

__Response Structure__

```
{
   "stat":1,
   "page":"5",
   "message":"Success",
   "reason":null,
   "result":{
      "id":4,
      "applicationId":6,
      "micr":"600751023",
      "address":"GROUND FLOOR, NO. 4/579OLD MAHABALIPURAM ROAD, RAMALINGA NAGARKOTTIVAKKAM, CHENNAI - 600041, TOLL FREE NO.- 18004194332",
      "branchName":null,
      "pincode":null,
      "ifsc":"IDFB0080138",
      "accountNo":"10088962428"
   },
   "address_response":null
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|applicationId	|String	| |
|micr	|String	| |
|address	|String	| |
|branchName	|String	| |
|pincode	|String	| |
|ifsc	|String	| |
|accountNo	|String	| |


### Get branch details

__Request Structure__ 

```
ifsc=IDFB0080138

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|ifsc	|String	|   

__Response Structure__

```
{
   "stat":1,
   "page":null,
   "message":"Success",
   "reason":null,
   "result":{
      "BRANCH":"CHENNAI KOTTIVAKKAM BRANCH",
      "NEFT":true,
      "CITY":"CHENNAI",
      "MICR":"600751023",
      "UPI":true,
      "STATE":"TAMIL NADU",
      "ISO3166":"IN-TN",
      "CONTACT":"",
      "RTGS":true,
      "DISTRICT":"CHENNAI",
      "ADDRESS":"GROUND FLOOR, NO. 4/579OLD MAHABALIPURAM ROAD, RAMALINGA NAGARKOTTIVAKKAM, CHENNAI - 600041, TOLL FREE NO.- 18004194332",
      "IMPS":true,
      "CENTRE":"CHENNAI",
      "BANK":"IDFC FIRST Bank",
      "BANKCODE":"IDFB",
      "IFSC":"IDFB0080138"
   },
   "address_response":null
}

```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|BRANCH	|String	|     |
|NEFT	|String	| |
|CITY	|String	| |
|MICR	|String	| |
|UPI	|String	| |
|STATE	|String	| |
|ISO3166	|String	| |
|CONTACT	|String	| |
|RTGS	|String	| |
|DISTRICT	|String	| |
|ADDRESS	|String	| |
|IMPS	|String	| |
|CENTRE	|String	| |
|BANK	|String	| |
|BANKCODE	|String	| |
|IFSC	|String	| |



### Save bank

__Request Structure__ 

```
{
   "applicationId":6,
   "micr":"600751023",
   "address":"GROUND FLOOR, NO. 4/579OLD MAHABALIPURAM ROAD, RAMALINGA NAGARKOTTIVAKKAM, CHENNAI - 600041, TOLL FREE NO.- 18004194332",
   "ifsc":"IDFB0080138",
   "accountNo":"10088962428"
}
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	|   
|micr	|String	| |
|address	|String	| |
|ifsc	|String	| |
|accountNo	|String	| |


__Response Structure__

```
{
   "stat":1,
   "page":"6",
   "message":"Success",
   "reason":null,
   "result":{
      "id":4,
      "applicationId":6,
      "micr":"600751023",
      "address":"GROUND FLOOR, NO. 4/579OLD MAHABALIPURAM ROAD, RAMALINGA NAGARKOTTIVAKKAM, CHENNAI - 600041, TOLL FREE NO.- 18004194332",
      "branchName":null,
      "pincode":null,
      "ifsc":"IDFB0080138",
      "accountNo":"10088962428"
   },
   "address_response":null
}

```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	| |
|applicationId	|String	|   
|micr	|String	| |
|address	|String	| |
|branchName	|String	| |
|pincode	|String	| |
|ifsc	|String	| |
|accountNo	|String	| |


## Segment Selection

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|segment/getSegment/?:applicationId  |Fetch Index Details|
| Post|segment/saveSegment |Get Multiple Index Details with titles|


### Get segment

__Request Structure__ 

```
applicationId

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	|   

__Response Structure__

```
{
   "stat":1,
   "page":"6",
   "message":"Success",
   "reason":null,
   "result":{
      "id":4,
      "applicationId":6,
      "allSegment":1,
      "equity":0,
      "derivatives":0,
      "aluminium":"FPOs/Farmers",
      "brass":"Others",
      "cardamom":"Others",
      "copper":"Others",
      "cotton":"Others",
      "crupalmoil":"Others",
      "crudeoil":"Others",
      "gold":"Others",
      "menthaoil":"Others",
      "naturalgas":"Others",
      "nickel":"Others",
      "pepper":"Others",
      "rbdpmolein":"Others",
      "silver":"Others",
      "zinc":"Others",
      "kapas":"Others",
      "rubber":"Others",
      "mcxbulldex":"Others",
      "mcxmetldex":"Others",
      "mcxcomdex":"Others",
      "lead":"Others"
   },
   "address_response":null
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|applicationId	|String	| |
|equity	|String	| |
|derivatives	|String	| |
|aluminium	|String	| |
|brass	|String	| |
|cardamom	|String	| |
|copper	|String	| |
|cotton	|String	| |
|crupalmoil	|String	| |
|crudeoil	|String	| |
|gold	|String	| |
|menthaoil	|String	| |
|naturalgas	|String	|     |
|nickel	|String	| |
|pepper	|String	| |
|rbdpmolein	|String	| |
|silver	|String	| |
|zinc	|String	| |
|kapas	|String	| |
|rubber	|String	| |
|mcxbulldex	|String	| |
|mcxmetldex	|String	| |
|mcxcomdex	|String	| |
|lead	|String	| |

### Save Segment

__Request Structure__ 

```
{
   "applicationId":6,
   "allSegment":1,
   "equity":0,
   "derivatives":0,
   "aluminium":"FPOs/Farmers",
   "brass":"Others",
   "cardamom":"Others",
   "copper":"Others",
   "cotton":"Others",
   "crupalmoil":"Others",
   "crudeoil":"Others",
   "gold":"Others",
   "menthaoil":"Others",
   "naturalgas":"Others",
   "nickel":"Others",
   "pepper":"Others",
   "rbdpmolein":"Others",
   "silver":"Others",
   "zinc":"Others",
   "kapas":"Others",
   "rubber":"Others",
   "mcxbulldex":"Others",
   "mcxmetldex":"Others",
   "mcxcomdex":"Others",
   "lead":"Others"
}
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	|     |
|allSegment	|String	| |
|equity	|String	| |
|derivatives	|String	| |
|aluminium	|String	| |
|brass	|String	| |
|cardamom	|String	| |
|copper	|String	| |
|cotton	|String	| |
|crupalmoil	|String	| |
|crudeoil	|String	| |
|gold	|String	| |
|menthaoil	|String	| |
|naturalgas	|String	|     |
|nickel	|String	| |
|pepper	|String	| |
|rbdpmolein	|String	| |
|silver	|String	| |
|zinc	|String	| |
|kapas	|String	| |
|rubber	|String	| |
|mcxbulldex	|String	| |
|mcxmetldex	|String	| |
|mcxcomdex	|String	| |
|lead	|String	| | 

__Response Structure__

```
{
   "stat":1,
   "page":"7",
   "message":"Success",
   "reason":null,
   "result":{
      "id":4,
      "applicationId":6,
      "allSegment":1,
      "equity":0,
      "derivatives":0,
      "aluminium":"FPOs/Farmers",
      "brass":"Others",
      "cardamom":"Others",
      "copper":"Others",
      "cotton":"Others",
      "crupalmoil":"Others",
      "crudeoil":"Others",
      "gold":"Others",
      "menthaoil":"Others",
      "naturalgas":"Others",
      "nickel":"Others",
      "pepper":"Others",
      "rbdpmolein":"Others",
      "silver":"Others",
      "zinc":"Others",
      "kapas":"Others",
      "rubber":"Others",
      "mcxbulldex":"Others",
      "mcxmetldex":"Others",
      "mcxcomdex":"Others",
      "lead":"Others"
   },
   "address_response":null
}

```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|applicationId	|String	| |
|allSegment	|String	| |
|equity	|String	| |
|derivatives	|String	| |
|aluminium	|String	| |
|brass	|String	| |
|cardamom	|String	| |
|copper	|String	| |
|cotton	|String	| |
|crupalmoil	|String	| |
|crudeoil	|String	| |
|gold	|String	| |
|menthaoil	|String	| |
|naturalgas	|String	|     |
|nickel	|String	| |
|pepper	|String	| |
|rbdpmolein	|String	| |
|silver	|String	| |
|zinc	|String	| |
|kapas	|String	| |
|rubber	|String	| |
|mcxbulldex	|String	| |
|mcxmetldex	|String	| |
|mcxcomdex	|String	| |
|lead	|String	| |

## Nominee

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|nominee/getNominee/?:applicationId  |Fetch Index Details|
| Post|nominee/saveNominee |Get Multiple Index Details with titles|


### Get Nominee

__Request Structure__ 

```
applicationId=6

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	|   

__Response Structure__

```
{
   "stat":1,
   "page":"8",
   "message":"Success",
   "reason":null,
   "result":[
      {
         "id":3,
         "applicationId":6,
         "nomineeId":"Nominee_1",
         "firstname":"RAMAN",
         "lastname":"K",
         "relationship":"Father",
         "dateOfbirth":"20-06-1976",
         "pancard":"",
         "mobilenumber":9832423413,
         "emailaddress":null,
         "address1":"Mulanur",
         "address2":"",
         "pincode":638106,
         "state":"Tamil Nadu",
         "attachementUrl":"/opt/files/doc/6/6_NOMINEE_PROOF.pdf",
         "allocation":100,
         "guardianEntity":null,
         "nomOneAllocation":0,
         "nomTwoAllocation":0,
         "nomThreeAllocation":0
      }
   ],
   "address_response":null
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|applicationId	|String	| |
|nomineeId	|String	| |
|firstName	|String	| |
|lastName	|String	| |
|relationship	|String	| |
|dateOfbirth	|String	| |
|pancard	|String	| |
|mobilenumber	|String	| |
|emailaddress	|String	| |
|address1	|String	| |
|address2	|String	| |
|pincode	|String	| |
|state	|String	| |
|attachementUrl	|String	| |
|allocation	|String	| |
|guardianEntity	|String	| |
|nomOneAllocation	|String	| |
|nomTwoAllocation	|String	| |
|nomThreeAllocation	|String	| |

### Save Nominee

__Request Structure__ 

```
applicationId: 6
file: (binary)
nomineeDetails: {
    "applicationId": "6",
    "firstname": "RAMAN",
    "lastname": "K",
    "relationship": "Father",
    "dateOfbirth": "20-06-1976",
    "pancard": "",
    "mobilenumber": 9832423413,
    "address1": "Mulanur",
    "address2": "",
    "pincode": 638106,
    "state": "Tamil Nadu",
    "nomOneAllocation": 100,
    "nomTwoAllocation": 0,
    "nomThreeAllocation": 0
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	|     |
|firstname	|String	| |
|lastname	|String	| |
|relationship	|String	| |
|dateOfbirth	|String	| |
|pancard	|String	| |
|mobilenumber	|String	| |
|address1	|String	| |
|address2	|String	| |
|pincode	|String	| |
|state	|String	| |
|nomOneAllocation	|String	| |
|nomTwoAllocation	|String	| |
|nomThreeAllocation	|String	|     |


__Response Structure__

```
{
   "stat":0,
   "page":null,
   "message":null,
   "reason":null,
   "result":{
      "stat":1,
      "page":"8.2",
      "message":"Success",
      "reason":null,
      "result":{
         "id":3,
         "applicationId":6,
         "nomineeId":"Nominee_1",
         "firstname":"RAMAN",
         "lastname":"K",
         "relationship":"Father",
         "dateOfbirth":"20-06-1976",
         "pancard":"",
         "mobilenumber":9832423413,
         "emailaddress":null,
         "address1":"Mulanur",
         "address2":"",
         "pincode":638106,
         "state":"Tamil Nadu",
         "attachementUrl":"/opt/files/doc/6/6_NOMINEE_PROOF.pdf",
         "allocation":100,
         "guardianEntity":null,
         "nomOneAllocation":0,
         "nomTwoAllocation":0,
         "nomThreeAllocation":0
      },
      "address_response":null
   },
   "address_response":null
}

```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|applicationId	|String	| |
|nomineeId	|String	| |
|firstName	|String	| |
|lastName	|String	| |
|relationship	|String	| |
|dateOfbirth	|String	| |
|pancard	|String	| |
|mobilenumber	|String	| |
|emailaddress	|String	| |
|address1	|String	| |
|address2	|String	| |
|pincode	|String	| |
|state	|String	| |
|attachementUrl	|String	| |
|allocation	|String	| |
|guardianEntity	|String	| |
|nomOneAllocation	|String	| |
|nomTwoAllocation	|String	| |
|nomThreeAllocation	|String	| |

## Payment

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|bank/createPayment  |Fetch Index Details|
| Post|bank/checkPayment/?:applicationId|Get Multiple Index Details with titles|
| Post|bank/verifyPayment  |Fetch Index Details|



### Create Payment

__Request Structure__ 

```
{
   "applicationId":1,
   "amount":1
}
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	|   
|amount	|String	|   


__Response Structure__

No body




<!-- |Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|userName	|String	| |
|firstName	|String	| |
|middleName	|String	| |
|lastName	|String	| |
|mobileNo	|String	| |
|emailId	|String	| |
|emailVerified	|String	| |
|smsVerified	|String	| |
|panNumber	|String	| |
|dob	|String	| |
|stage	|String	| |
|status	|String	| | -->

### Check Payment

__Request Structure__ 

```
applicationId=1
```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	|   

__Response Structure__

NO body

<!-- __parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|userName	|String	| |
|firstName	|String	| |
|middleName	|String	| |
|lastName	|String	| |
|mobileNo	|String	| |
|emailId	|String	| |
|emailVerified	|String	| |
|smsVerified	|String	| |
|panNumber	|String	| |
|dob	|String	| |
|stage	|String	| |
|status	|String	| | -->

### verify Payment

__Request Structure__ 

```
{
   "razorpayOrderId":"",
   "razorpayPaymentId":"order_LDVmKnAEvvhIAT",
   "razorpaySignature":"",
   "receipt":"1",
   "amount":1
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|razorpayOrderId	|String	|  |
|razorpayPaymentId	|String	|  |
|razorpaySignature	|String	|  |
|receipt	|String	|  |
|amount	|String	|  |



__Response Structure__

NO body




## Document Upload

|Method	     |API   	|Detail        |
|------------|----------|------------------ |
| Post|doc/upload/  |Fetch Index Details|


### Save document 

__Request Structure__ 

```
{
applicationId: 6
typeOfProof: Cheque_Statement
password: 12345
file: (binary)
}

```

__Input parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|applicationId	|String	|   |
|typeOfProof	|String	|   
|password	|String	|   
|file	|String	|   


__Response Structure__

```
{
   "stat":0,
   "page":null,
   "message":"Success",
   "reason":null,
   "result":{
      "id":5,
      "applicationId":6,
      "attachement":"application/pdf",
      "attachementUrl":"/opt/files/doc/6/6_Cheque_Statement.pdf",
      "typeOfProof":"Cheque_Statement",
      "password":"12345",
      "latitude":null,
      "longitude":null
   },
   "address_response":null
}
```

__parameters__


|Field	| Type	|Description|
|-------|-------------------|-------------------------------|
|id	|String	|     |
|applicationId	|String	| |
|attachement	|String	| |
|attachementUrl	|String	| |
|typeOfProof	|String	| |
|password	|String	| |
|latitude	|String	| |
|longitude	|String	| |



## IPV


## ESign


