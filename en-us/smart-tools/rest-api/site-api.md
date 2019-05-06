---
layout: doc
---
# Site API

## /site/installAgent/{siteId}

### Description

Update the Delivery Group configuration for a Site.

### URL Structure

`https://SERVERNAME/v0/site/installAgent/{site_id}?fqdn=FQDN_ID&access_token=VALID_ACCESS_TOKEN`

### Method

PUT

### Response

JSON

Sample response:

Returns task key(String)

## /site/{siteId}/sitecomponentdetails

### Description

Fetches the Site component details

### URL Structure

`https://SERVERNAME/v0/site/{siteId}/sitecomponentdetails?limit=LIMIT&offset=OFFSET&access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

JSON

Sample response:

```json
[
   {
      "companyId":10095,
      "ddcAvailable":"Available",
      "ddcName":"XDC.xspoc.local",
      "fqdn":"XDC.xspoc.local",
      "agentInstalled":"Installed",
      "agentActive":"Active",
      "siteId":196,
      "timeZone":"Pacific Standard Time",
      "extraAttrs":{

      },
      "agentOnline":"Online"
   }
]
```

## /site/{siteId}

### Description

Fetches the Site details for site Id

### URL Structure

`https://SERVERNAME/v0/site/{siteId}?access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

JSON

Sample response:

```json
{
   "role":"Admin",
   "updateCount":-1,
   "description":"",
   "hotFixCount":-1,
   "deliverygroupCount":-1,
   "customerSiteId":"3ba7f169-63cc-46fb-8cc7-7d49503a6fe5",
   "upgradeServiceStatus":"Site Onboarded",
   "customerSiteName":"XS Automation Site",
   "totalServerCount":-1,
   "lastUpdateTimestamp":{
      "dayOfWeek":"MONDAY",
      "hour":19,
      "month":"JANUARY",
      "dayOfYear":30,
      "dayOfMonth":30,
      "year":2017,
      "monthValue":1,
      "nano":612000000,
      "chronology":{
         "calendarType":"iso8601",
         "id":"ISO"
      },
      "minute":11,
      "second":41
   },
   "sessionCount":-1,
   "citrixOrgId":"int010139e5",
   "analysisProcessId":132347,
   "creationTimestamp":{
      "dayOfWeek":"THURSDAY",
      "hour":18,
      "month":"JANUARY",
      "dayOfYear":26,
      "dayOfMonth":26,
      "year":2017,
      "monthValue":1,
      "nano":29000000,
      "chronology":{
         "calendarType":"iso8601",
         "id":"ISO"
      },
      "minute":14,
      "second":6
   },
   "id":196,
   "extraAttrs":{

   },
   "deploymentJobDetailId":0,
   "activeServerCount":-1,
   "backgroundJobId":90767,
   "smartScaleServiceStatus":"Site Onboarded",
   "companyId":10095,
   "smartScaleStatusMessage":"",
   "upgradeStatusMessage":"",
   "name":"XS Automation Site",
   "siteAgentBeanList":[
      {
         "ddcFqdn":"XDC.xspoc.local",
         "ddcAddress":"",
         "companyId":0,
         "password":"xZzotQI3ek5nm6VVJfsD0EfhrPA7WKy12TCRlyZJvp9O8CKFX2y+FEEJfWEU4R81RdXWiSVGqEyee5atzHCBuQp/0KYSJb7V/onulFEcnX7eb10Rg4igKj8w1RSvH+Usd9w1rZbvKVBD/+eqbLQqCz9xKYTnxI3TXga/QU13d0E=",
         "role":"Admin",
         "salt":"c929a135-b59b-4164-82dc-b744b1ec535f",
         "siteAgentId":"1502",
         "siteId":196,
         "userName":"xspoc\\administrator",
         "user":"-999",
         "extraAttrs":{

         },
         "activeFlag":"Y"
      }
   ],
   "user":"46148",
   "siteDetailBeans":[
      {
         "propertyKey":"activeservers",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"1",
         "user":"44864",
         "extraAttrs":{

         }
      },
      {
         "propertyKey":"totalservers",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"2",
         "user":"44864",
         "extraAttrs":{

         }
      },
      {
         "propertyKey":"sessionCount",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"0",
         "user":"44864",
         "extraAttrs":{

         }
      },
      {
         "propertyKey":"deliverygroups",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"1",
         "user":"44864",
         "extraAttrs":{

         }
      },
      {
         "propertyKey":"deploymentType",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"traditional",
         "user":"46148",
         "extraAttrs":{

         }
      },
      {
         "propertyKey":"analysisProjectId",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"132344",
         "user":"44864",
         "extraAttrs":{

         }
      },
      {
         "propertyKey":"analysisProjectIdForSiteHealthCheck",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"132345",
         "user":"44864",
         "extraAttrs":{

         }
      },
      {
         "propertyKey":"analysisProjectIdForAppsDesktopHealthCheck",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"132346",
         "user":"44864",
         "extraAttrs":{

         }
      },
      {
         "propertyKey":"analysisProjectIdForLTSRCheck",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"132347",
         "user":"44864",
         "extraAttrs":{

         }
      }
   ]
}
```

## /site/{siteId}/credentials

### Description

Edit the Site credentials for a specific Site created

### URL Structure

`https://SERVERNAME/v0/site/{siteId}/credentials?access_token=VALID_ACCESS_TOKEN`

### Payload

`{"password":ENCRYPTED_PASSWORD,"userName":USER_NAME}`

### Method

PUT

### Response

JSON

Sample response:

```json
{
   "role":"Admin",
   "updateCount":-1,
   "description":"",
   "hotFixCount":-1,
   "deliverygroupCount":-1,
   "customerSiteId":"3ba7f169-63cc-46fb-8cc7-7d49503a6fe5",
   "upgradeServiceStatus":"Site Onboarded",
   "customerSiteName":"XS Automation Site",
   "totalServerCount":-1,
   "lastUpdateTimestamp":{
      "dayOfWeek":"FRIDAY",
      "hour":23,
      "month":"JANUARY",
      "dayOfYear":27,
      "dayOfMonth":27,
      "year":2017,
      "monthValue":1,
      "nano":740000000,
      "chronology":{
         "calendarType":"iso8601",
         "id":"ISO"
      },
      "minute":9,
      "second":34
   },
   "sessionCount":-1,
   "citrixOrgId":"int010139e5",
   "analysisProcessId":132347,
   "creationTimestamp":{
      "dayOfWeek":"THURSDAY",
      "hour":18,
      "month":"JANUARY",
      "dayOfYear":26,
      "dayOfMonth":26,
      "year":2017,
      "monthValue":1,
      "nano":29000000,
      "chronology":{
         "calendarType":"iso8601",
         "id":"ISO"
      },
      "minute":14,
      "second":6
   },
   "id":196,
   "extraAttrs":{
   },
   "deploymentJobDetailId":0,
   "activeServerCount":-1,
   "backgroundJobId":90767,
   "smartScaleServiceStatus":"Site Onboarded",
   "companyId":10095,
   "smartScaleStatusMessage":"",
   "upgradeStatusMessage":"",
   "name":"XS Automation Site",
   "siteAgentBeanList":[
      {
         "ddcFqdn":"XDC.xspoc.local",
         "ddcAddress":"",
         "companyId":0,   "password":"tB5MHAW0o7fMIB8BMLsTte+KNYDaUcBmG9JGqSwi95AcXM/s3R7RRbx2Ll+lBsCW1gWkEgwS4I5CNlXprDH5NW1oouMsmrpy+dn647s08ZZqoDAZ6lKEltV0mHGhpEIud9w1rZbvKVBD/+eqbLQqCz9xKYTnxI3TXga/QU13d0E=",
         "role":"Admin",
         "salt":"33c95e32-35bb-4c6a-9553-f14e6f5fdba8",
         "siteAgentId":"1502",
         "siteId":196,
         "userName":"xspoc\\administrator",
         "user":"-999",
         "extraAttrs":{
         },
         "activeFlag":"Y"
      }
   ],
   "user":"46148",
   "siteDetailBeans":[
      {
         "propertyKey":"deploymentType",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"traditional",
         "user":"17284",
         "extraAttrs":{
         }
      },
      {
         "propertyKey":"analysisProjectId",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"132344",
         "user":"44864",
         "extraAttrs":{
         }
      },
      {
         "propertyKey":"analysisProjectIdForSiteHealthCheck",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"132345",
         "user":"44864",
         "extraAttrs":{
         }
      },
      {
         "propertyKey":"analysisProjectIdForAppsDesktopHealthCheck",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"132346",
         "user":"44864",
         "extraAttrs":{
         }
      },
      {
         "propertyKey":"analysisProjectIdForLTSRCheck",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"132347",
         "user":"44864",
         "extraAttrs":{
         }
      },
      {
         "propertyKey":"activeservers",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"1",
         "user":"44864",
         "extraAttrs":{
         }
      },
      {
         "propertyKey":"totalservers",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"2",
         "user":"44864",
         "extraAttrs":{
         }
      },
      {
         "propertyKey":"sessionCount",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"0",
         "user":"44864",
         "extraAttrs":{
         }
      },
      {
         "propertyKey":"deliverygroups",
         "companyId":0,
         "role":"Admin",
         "siteId":196,
         "propertyValue":"1",
         "user":"44864",
         "extraAttrs":{
         }
      }
   ]
}
```

## /download/siteagentinfo

### Description

Fetches the Smart Tools Agent download exec information.

### URL Structure

`https://SERVERNAME/v0/download/siteagentinfo?access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

JSON

Sample response:

```json
{
"filename":"CitrixSmartToolsAgent.exe",
   "link":"https://cloudmanage.scalextreme.com/downloadfile/agent/win32/8bd0f8f3-6352-42ed-bf3b-b58b570977eb/CitrixSmartToolsAgent.exe",
   "downloadKey":"8bd0f8f3-6352-42ed-bf3b-b58b570977eb",
   "arch":"win32"
}
```