---
layout: doc
---
# Smart Scale API

> **Important:**
>
> This article includes references to Smart Scale which will reach End of Life on **May 31, 2019**. For more information about Smart Scale deprecation, see the following articles:
>
> *  [What's New in Smart Tools](https://docs.citrix.com/en-us/smart-tools/whats-new.html)
> *  [Deprecation](https://docs.citrix.com/en-us/citrix-virtual-apps-desktops/whats-new/removed-features.html) in Virtual Apps and Desktops

## /smartscale/{siteId}/deliverygroups

### Description

Fetch all the Delivery Groups along with their detail for a siteId.

### URL Structure

`https://SERVERNAME/v0/smartscale/{siteId}/deliverygroups?access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

JSON

Sample response:

```json
{
   "companyId":0,
   "extraAttrs":{
      "deliverygroups":[
         {
            "companyId":10095,
            "role":"Admin",
            "deliveryGroupName":"Automation Delivery Group",
            "deliveryGroupDetailBean":[
               {
                  "propertyKey":"SESSIONS",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62195,
                  "propertyValue":"0",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               },
               {
                  "propertyKey":"TOTAL_DESKTOPS",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62196,
                  "propertyValue":"2",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               },
               {
                  "propertyKey":"DESKTOPS_AVAILABLE",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62197,
                  "propertyValue":"1",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               },
               {
                  "propertyKey":"TimeZone",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62198,
                  "propertyValue":"Pacific Standard Time",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               },
               {
                  "propertyKey":"Enabled",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62199,
                  "propertyValue":"N",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               },
               {
                  "propertyKey":"config",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62200,
                  "propertyValue":"{\"companyId\":0,\"extraAttrs\":{},\"jobId\":90657,\"price\":0.06,\"unit\":\"hour\",\"currency\":\"USD\"}",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               },
               {
                  "propertyKey":"vdaCount",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62201,
                  "propertyValue":"2",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               },
               {
                  "propertyKey":"availVdaCount",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62202,
                  "propertyValue":"1",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               },
               {
                  "propertyKey":"unregVdaCount",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62203,
                  "propertyValue":"0",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               },
               {
                  "propertyKey":"maintVdaCount",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62204,
                  "propertyValue":"0",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               },
               {
                  "propertyKey":"busyVdaCount",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62205,
                  "propertyValue":"0",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               },
               {
                  "propertyKey":"type",
                  "companyId":0,
                  "role":"Admin",
                  "deliveryGroupDetailId":62206,
                  "propertyValue":"rds",
                  "user":"44864",
                  "deliveryGroupId":177,
                  "extraAttrs":{

                  }
               }
            ],
            "description":"null",
            "siteId":188,
            "minServers":1,
            "user":"44864",
            "deliveryGroupId":177,
            "uuid":"4f90f745-068c-475c-9c90-c0256b512fc5",
            "extraAttrs":{

            }
         }
      ]
   }
}
```

## /smartscale/updateSite

### Description

Adds Site, rather triggers add Site

### URL Structure

`https://SERVERNAME/v0/smartscale/updateSite&access_token=VALID_ACCESS_TOKEN`

### Payload

```json
{"siteDetailBeans":[{"propertyKey":"siteAgentId","propertyValue":AGENT_ID},{"propertyKey":"user","propertyValue":USER},{"propertyKey":"password","propertyValue":PASSWORD}]}
```

`PASSWORD` is the encrypted password retrieved from the /acls/encrypt.

### Method

GET

### Response

JSON

Sample response:

```json
{
   "companyId":10116,
   "role":"Admin",
   "user":"44864",
   "id":345,
   "name":"DC - 685",
   "description":"",
   "customerSiteId":"",
   "customerSiteName":"",
   "analysisProcessId":0,
   "deploymentJobDetailId":0,
   "upgradeServiceStatus":"Failed to Onboard Site",
   "smartScaleServiceStatus":"Update In Progress",
   "creationTimestamp":{
      "hour":18,
      "minute":6,
      "second":10,
      "nano":134000000,
      "dayOfYear":27,
      "dayOfWeek":"FRIDAY",
      "month":"JANUARY",
      "dayOfMonth":27,
      "year":2017,
      "monthValue":1,
      "chronology":{
         "id":"ISO",
         "calendarType":"iso8601"
      }
   },
   "lastUpdateTimestamp":{
      "hour":19,
      "minute":49,
      "second":2,
      "nano":741000000,
      "dayOfYear":27,
      "dayOfWeek":"FRIDAY",
      "month":"JANUARY",
      "dayOfMonth":27,
      "year":2017,
      "monthValue":1,
      "chronology":{
         "id":"ISO",
         "calendarType":"iso8601"
      }
   },
   "smartScaleStatusMessage":"Starting Update",
   "upgradeStatusMessage":"call failed, host: A685C10116, error: The user name or password is incorrect.",
   "backgroundJobId":0,
   "siteAgentBeanList":[
      {
         "companyId":0,
         "role":"Admin",
         "user":"-999",
         "extraAttrs":{

         },
         "activeFlag":"Y",
         "siteAgentId":"685",
         "ddcAddress":"10.62.137.7",
         "ddcFqdn":"DC.xensxdpoc12.com",
         "siteId":345,
         "userName":"domain\username",
         "salt":"5319a1de-8ddd-4cd9-ae4d-c8ba4d5eac28",
         "password":"yDEXJ70/aUy48cKBbfUdRjBlUmih0iVPbNmdd0PwXiEygq/bUp+htqytXrnMjvW/edve3z6OrFBPLIouDCOfU0Tm35bj+6HzPjyOxsO/3kszcDeiLGblPl5SO1vNKwGyIf8fr10uqt280+vX+D9q6LqA3AUrvmxHEwdYNs0ual4="
      }
   ],
   "hotFixCount":-1,
   "activeServerCount":-1,
   "totalServerCount":-1,
   "deliverygroupCount":-1,
   "sessionCount":-1,
   "siteDetailBeans":[

   ],
   "updateCount":-1
}
```

## /smartscale/updateDeliveryGroupConfig

### Description

Update the Delivery Group configuration for a Site.

### URL Structure

`https://SERVERNAME/v0/smartscale/updateDeliveryGroupConfig?access_token=VALID_ACCESS_TOKEN`

### Method

PUT

### Payload

```json
{"companyId":COMPANY_ID,"role":ROLE, "user":USER, "deliveryGroupId":DELIVERY_GROUP_ID, "deliveryGroupName":DELIVERY_GROUP_NAME, "description":DESCRIPTION, "uuid":UUID, "siteId":SITE_ID, "minServers":MINIMUM_SERVERS,"deliveryGroupDetailBean":[{"companyId":COMPANY_ID, "role":ROLE, "user":USER, "deliveryGroupDetailId":DELIVERY_GROUP_DETAIL_ID, "deliveryGroupId":DELIVERY_GROUP_ID, "propertyKey":PROPERTY_KEY, "propertyValue":PROPERTY_VALUE}]}
```

### Response

JSON

Sample response:

```json
{
   "companyId":0,
   "role":"Admin",
   "user":"44834",
   "extraAttrs":{

   },
   "deliveryGroupId":82,
   "deliveryGroupName":"DeliveryGroup1",
   "description":"null",
   "uuid":"39ebfe58-b085-45e4-87b9-36f90afe893e",
   "siteId":112,
   "minServers":1,
   "activeFlag":"Y",
   "deliveryGroupDetailBean":[
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1069,
         "deliveryGroupId":82,
         "propertyKey":"vdaCount",
         "propertyValue":"1"
      },
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1070,
         "deliveryGroupId":82,
         "propertyKey":"availVdaCount",
         "propertyValue":"0"
      },
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1071,
         "deliveryGroupId":82,
         "propertyKey":"unregVdaCount",
         "propertyValue":"1"
      },
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1072,
         "deliveryGroupId":82,
         "propertyKey":"maintVdaCount",
         "propertyValue":"1"
      },
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1073,
         "deliveryGroupId":82,
         "propertyKey":"busyVdaCount",
         "propertyValue":"0"
      },
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1074,
         "deliveryGroupId":82,
         "propertyKey":"type",
         "propertyValue":"vdi"
      },
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1037,
         "deliveryGroupId":82,
         "propertyKey":"Enabled",
         "propertyValue":"N"
      },
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1038,
         "deliveryGroupId":82,
         "propertyKey":"config",
         "propertyValue":"{\"companyId\":0,\"extraAttrs\":{},\"jobId\":1070,\"schedules\":[],\"capacityManagement\":{\"companyId\":0,\"extraAttrs\":{},\"scheduleType\":\"timeandloadbased\",\"metricType\":\"SESSION_COUNT\",\"maxSessionsPerServer\":2,\"maxLoadIndexPerServer\":10000,\"bufferCapacity\":10},\"price\":0.06,\"unit\":\"hour\",\"currency\":\"USD\"}"
      },
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1033,
         "deliveryGroupId":82,
         "propertyKey":"SESSIONS",
         "propertyValue":"0"
      },
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1034,
         "deliveryGroupId":82,
         "propertyKey":"TOTAL_DESKTOPS",
         "propertyValue":"1"
      },
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1035,
         "deliveryGroupId":82,
         "propertyKey":"DESKTOPS_AVAILABLE",
         "propertyValue":"0"
      },
      {
         "companyId":0,
         "role":"Admin",
         "user":"44834",
         "extraAttrs":{

         },
         "deliveryGroupDetailId":1036,
         "deliveryGroupId":82,
         "propertyKey":"TimeZone",
         "propertyValue":"Eastern Standard Time"
      }
   ]
}
```

## /smartscale/{agentId}/existingsite

### Description

Validate if the agent has already been added on to the existing Site

### URL Structure

`https://SERVERNAME/v0/smartscale/{agentId}/existingsite?access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

JSON

Sample response:

If the agent is already installed: "Site onboarding has been completed and there is no need of adding site for the siteId:"

If the agent is not installed: "Site onboarding has not been completed. So, please go ahead and add site for the siteId:"

## /smartscale/events/{deliveryGroupId}/step/{stepId}

### Description

Fetch the machine activity information based of the specific Delivery Group and the stepId.

### URL Structure

`https://SERVERNAME/v0/smartscale/events/{deliveryGroupId}/step/{stepId}?access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

JSON

Sample response:

```json
[{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":8546,"jobId":2020117,"deliveryGroupId":586,"machineUid":38,"machineName":"Sheva512VDI04.sheva-qaaws0512.com","initialState":"POWER_OFF","currentState":"POWER_OFF","lastTimeMillis":1499277040863,"creationTimestamp":{"hour":17,"minute":0,"second":48,"nano":917000000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":17,"minute":50,"second":40,"nano":863642000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1499274048917,"lastUpdateTimeMillis":1499277040863,"targetState":"POWER_ON","status":"failed"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":8545,"jobId":2020117,"deliveryGroupId":586,"machineUid":35,"machineName":"Sheva512VDI05.sheva-qaaws0512.com","initialState":"POWER_OFF","currentState":"POWER_OFF","lastTimeMillis":1499277040857,"creationTimestamp":{"hour":17,"minute":0,"second":48,"nano":906000000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":17,"minute":50,"second":40,"nano":857431000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1499274048906,"lastUpdateTimeMillis":1499277040857,"targetState":"POWER_ON","status":"failed"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":8544,"jobId":2020117,"deliveryGroupId":586,"machineUid":37,"machineName":"Sheva512VDI02.sheva-qaaws0512.com","initialState":"POWER_OFF","currentState":"POWER_OFF","lastTimeMillis":1499277040850,"creationTimestamp":{"hour":17,"minute":0,"second":48,"nano":894000000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":17,"minute":50,"second":40,"nano":850757000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1499274048894,"lastUpdateTimeMillis":1499277040850,"targetState":"POWER_ON","status":"failed"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":8543,"jobId":2020117,"deliveryGroupId":586,"machineUid":34,"machineName":"Sheva512VDI03.sheva-qaaws0512.com","initialState":"POWER_OFF","currentState":"POWER_OFF","lastTimeMillis":1499277040844,"creationTimestamp":{"hour":17,"minute":0,"second":48,"nano":883000000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":17,"minute":50,"second":40,"nano":844383000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1499274048883,"lastUpdateTimeMillis":1499277040844,"targetState":"POWER_ON","status":"failed"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":8542,"jobId":2020117,"deliveryGroupId":586,"machineUid":38,"machineName":"Sheva512VDI04.sheva-qaaws0512.com","initialState":"inmaintenance","currentState":"outmaintenance","lastTimeMillis":1499274340973,"creationTimestamp":{"hour":17,"minute":0,"second":43,"nano":615000000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":17,"minute":5,"second":40,"nano":973000000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1499274043615,"lastUpdateTimeMillis":1499274340973,"targetState":"outmaintenance","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":8541,"jobId":2020117,"deliveryGroupId":586,"machineUid":35,"machineName":"Sheva512VDI05.sheva-qaaws0512.com","initialState":"inmaintenance","currentState":"outmaintenance","lastTimeMillis":1499274340973,"creationTimestamp":{"hour":17,"minute":0,"second":43,"nano":605000000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":17,"minute":5,"second":40,"nano":973000000,"dayOfYear":186,"dayOfWeek":"WEDNESDAY","month":"JULY","dayOfMonth":5,"year":2017,"monthValue":7,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1499274043605,"lastUpdateTimeMillis":1499274340973,"targetState":"outmaintenance","status":"complete"}]
```

## /smartscale/events/{jobId}

### Description

Fetches a list of StepRunLogBean based of the jobId and the selected time in history opted by the user.

### URL Structure

`https://SERVERNAME/v0/smartscale/events/{jobId}??timeBeforeInMillis=VALID_TIME_BEFORE_IN_MILLISECONDS &access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

JSON

Sample response:

```json
[{"companyId":40435,"extraAttrs":{},"stepRunId":1999816,"stepId":2001364,"jobDetailId":981,"projectRunId":1998512,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"complete","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1498225305768,"updatedAt":1498225306081,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":1999816,"outputText":" \nError resolved. Smart Scale is no longer experiencing errors.","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}},{"companyId":40435,"extraAttrs":{},"stepRunId":1999827,"stepId":2001375,"jobDetailId":981,"projectRunId":1998523,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"failed","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1498226110697,"updatedAt":1498226116074,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":1999827,"outputText":"Powering on 1 machine(s). \nEvent ID: 2001375, Initial # of machine(s) on: 1, Expected: 2\. Smart Scale event was unsuccessful. Smart Tools could not perform any power actions.","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}},{"companyId":40435,"extraAttrs":{},"stepRunId":2003981,"stepId":2005537,"jobDetailId":981,"projectRunId":2002670,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"complete","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1498501810809,"updatedAt":1498501811265,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":2003981,"outputText":" \nError resolved. Smart Scale is no longer experiencing errors.","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}},{"companyId":40435,"extraAttrs":{},"stepRunId":2004006,"stepId":2005562,"jobDetailId":981,"projectRunId":2002694,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"failed","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1498503311033,"updatedAt":1498503316597,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":2004006,"outputText":"Powering off 2 machine(s). \nEvent ID: 2005562, Initial # of machines on: 4, Expected: 2\. Smart Scale event was unsuccessful. Smart Tools could not perform any power actions.","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}},{"companyId":40435,"extraAttrs":{},"stepRunId":2004687,"stepId":2006245,"jobDetailId":981,"projectRunId":2003375,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"complete","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1498551635831,"updatedAt":1498551642061,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":2004687,"outputText":"Putting 2 machine(s) into maintenance mode\nEvent ID: 2006245, Initial # of machines on: 4, Expected: 2\. ","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}},{"companyId":40435,"extraAttrs":{},"stepRunId":2004691,"stepId":2006249,"jobDetailId":981,"projectRunId":2003379,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"complete","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1498551911727,"updatedAt":1498551920661,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":2004691,"outputText":"Powering off 2 machine(s). \nEvent ID: 2006249, Initial # of machines on: 4, Expected: 2\. ","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}},{"companyId":40435,"extraAttrs":{},"stepRunId":2004695,"stepId":2006253,"jobDetailId":981,"projectRunId":2003383,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"complete","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1498552210899,"updatedAt":1498552218077,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":2004695,"outputText":"Powering on 2 machine(s). \nEvent ID: 2006253, Initial # of machine(s) on: 2, Expected: 4\. ","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}},{"companyId":40435,"extraAttrs":{},"stepRunId":2004703,"stepId":2006261,"jobDetailId":981,"projectRunId":2003391,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"complete","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1498552811109,"updatedAt":1498552818975,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":2004703,"outputText":"Putting 3 machine(s) into maintenance mode\nEvent ID: 2006261, Initial # of machines on: 4, Expected: 1\. ","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}},{"companyId":40435,"extraAttrs":{},"stepRunId":2004707,"stepId":2006265,"jobDetailId":981,"projectRunId":2003395,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"complete","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1498553110926,"updatedAt":1498553119245,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":2004707,"outputText":"Powering off 3 machine(s). \nEvent ID: 2006265, Initial # of machines on: 4, Expected: 1\. ","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}},{"companyId":40435,"extraAttrs":{},"stepRunId":2015033,"stepId":2016623,"jobDetailId":981,"projectRunId":2013735,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"failed","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1499101811499,"updatedAt":1499101811854,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":2015033,"outputText":" \nUnsuccessful connection to XD/XenExpress service for fetchStateResponse API  Internal Server Error with status 500","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}},{"companyId":40435,"extraAttrs":{},"stepRunId":2015049,"stepId":2016639,"jobDetailId":981,"projectRunId":2013751,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"complete","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1499102410702,"updatedAt":1499102411713,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":2015049,"outputText":" \nError resolved. Smart Scale is no longer experiencing errors.","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}},{"companyId":40435,"extraAttrs":{},"stepRunId":2018600,"stepId":2020192,"jobDetailId":981,"projectRunId":2017300,"stepOutputType":1,"stepType":"step","stepExitCode":"","runStatus":"failed","remoteServerName":"","stepTag":"","stepTagLoc":"","activeFlag":"Y","createdAt":1499279710911,"updatedAt":1499279711316,"processInstanceRunId":0,"executionSequence":0,"stepRunLogOutputBean":{"companyId":0,"extraAttrs":{},"stepRunId":2018600,"outputText":" \nSmart Tools can't find any machines for the Delivery Group.","activeFlag":"Y"},"targetDetailBean":{"companyId":0,"extraAttrs":{},"agentId":0}}]
```

## /smartscale/machineactivity/{deliveryGroupId}

### Description

Fetch the list of Smart Scale events (list of machine activities) based on the specific Delivery Group ID and the selected time in history opted by the user.

### URL Structure

`https://SERVERNAME/v0/smartscale/machineactivity/{deliveryGroupId}?timeBeforeInMillis=VALID_TIME_BEFORE_IN_MILLISECONDS &access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

JSON

Sample response:

```json
[{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7243,"jobId":2006265,"deliveryGroupId":584,"machineUid":30,"machineName":"Sheva512RDS04.sheva-qaaws0512.com","initialState":"inmaintenance","currentState":"outmaintenance","lastTimeMillis":1498553411325,"creationTimestamp":{"hour":8,"minute":45,"second":18,"nano":977000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":50,"second":11,"nano":325000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498553118977,"lastUpdateTimeMillis":1498553411325,"targetState":"outmaintenance","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7242,"jobId":2006265,"deliveryGroupId":584,"machineUid":29,"machineName":"Sheva512RDS03.sheva-qaaws0512.com","initialState":"inmaintenance","currentState":"outmaintenance","lastTimeMillis":1498553411325,"creationTimestamp":{"hour":8,"minute":45,"second":18,"nano":967000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":50,"second":11,"nano":325000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498553118967,"lastUpdateTimeMillis":1498553411325,"targetState":"outmaintenance","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7241,"jobId":2006265,"deliveryGroupId":584,"machineUid":33,"machineName":"Sheva512RDS01.sheva-qaaws0512.com","initialState":"inmaintenance","currentState":"outmaintenance","lastTimeMillis":1498553411325,"creationTimestamp":{"hour":8,"minute":45,"second":18,"nano":949000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":50,"second":11,"nano":325000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498553118949,"lastUpdateTimeMillis":1498553411325,"targetState":"outmaintenance","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7239,"jobId":2006265,"deliveryGroupId":584,"machineUid":30,"machineName":"Sheva512RDS04.sheva-qaaws0512.com","initialState":"POWER_ON","currentState":"POWER_OFF","lastTimeMillis":1498553411325,"creationTimestamp":{"hour":8,"minute":45,"second":15,"nano":900000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":50,"second":11,"nano":325000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498553115900,"lastUpdateTimeMillis":1498553411325,"targetState":"POWER_OFF","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7238,"jobId":2006265,"deliveryGroupId":584,"machineUid":29,"machineName":"Sheva512RDS03.sheva-qaaws0512.com","initialState":"POWER_ON","currentState":"POWER_OFF","lastTimeMillis":1498553411325,"creationTimestamp":{"hour":8,"minute":45,"second":15,"nano":884000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":50,"second":11,"nano":325000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498553115884,"lastUpdateTimeMillis":1498553411325,"targetState":"POWER_OFF","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7237,"jobId":2006265,"deliveryGroupId":584,"machineUid":33,"machineName":"Sheva512RDS01.sheva-qaaws0512.com","initialState":"POWER_ON","currentState":"POWER_OFF","lastTimeMillis":1498553411325,"creationTimestamp":{"hour":8,"minute":45,"second":15,"nano":867000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":50,"second":11,"nano":325000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498553115867,"lastUpdateTimeMillis":1498553411325,"targetState":"POWER_OFF","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7235,"jobId":2006261,"deliveryGroupId":584,"machineUid":30,"machineName":"Sheva512RDS04.sheva-qaaws0512.com","initialState":"outmaintenance","currentState":"inmaintenance","lastTimeMillis":1498553111285,"creationTimestamp":{"hour":8,"minute":40,"second":18,"nano":719000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":45,"second":11,"nano":285000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498552818719,"lastUpdateTimeMillis":1498553111285,"targetState":"inmaintenance","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7234,"jobId":2006261,"deliveryGroupId":584,"machineUid":29,"machineName":"Sheva512RDS03.sheva-qaaws0512.com","initialState":"outmaintenance","currentState":"inmaintenance","lastTimeMillis":1498553111285,"creationTimestamp":{"hour":8,"minute":40,"second":18,"nano":708000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":45,"second":11,"nano":285000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498552818708,"lastUpdateTimeMillis":1498553111285,"targetState":"inmaintenance","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7233,"jobId":2006261,"deliveryGroupId":584,"machineUid":33,"machineName":"Sheva512RDS01.sheva-qaaws0512.com","initialState":"outmaintenance","currentState":"inmaintenance","lastTimeMillis":1498553111285,"creationTimestamp":{"hour":8,"minute":40,"second":18,"nano":304000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":45,"second":11,"nano":285000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498552818304,"lastUpdateTimeMillis":1498553111285,"targetState":"inmaintenance","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7232,"jobId":2006253,"deliveryGroupId":584,"machineUid":29,"machineName":"Sheva512RDS03.sheva-qaaws0512.com","initialState":"POWER_OFF","currentState":"POWER_ON","lastTimeMillis":1498552511131,"creationTimestamp":{"hour":8,"minute":30,"second":17,"nano":833000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":35,"second":11,"nano":131000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498552217833,"lastUpdateTimeMillis":1498552511131,"targetState":"POWER_ON","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7231,"jobId":2006253,"deliveryGroupId":584,"machineUid":33,"machineName":"Sheva512RDS01.sheva-qaaws0512.com","initialState":"POWER_OFF","currentState":"POWER_ON","lastTimeMillis":1498552511131,"creationTimestamp":{"hour":8,"minute":30,"second":17,"nano":821000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":35,"second":11,"nano":131000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498552217821,"lastUpdateTimeMillis":1498552511131,"targetState":"POWER_ON","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7230,"jobId":2006249,"deliveryGroupId":584,"machineUid":29,"machineName":"Sheva512RDS03.sheva-qaaws0512.com","initialState":"inmaintenance","currentState":"outmaintenance","lastTimeMillis":1498552211228,"creationTimestamp":{"hour":8,"minute":25,"second":20,"nano":417000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":30,"second":11,"nano":228000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498551920417,"lastUpdateTimeMillis":1498552211228,"targetState":"outmaintenance","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7229,"jobId":2006249,"deliveryGroupId":584,"machineUid":33,"machineName":"Sheva512RDS01.sheva-qaaws0512.com","initialState":"inmaintenance","currentState":"outmaintenance","lastTimeMillis":1498552211228,"creationTimestamp":{"hour":8,"minute":25,"second":20,"nano":406000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":30,"second":11,"nano":228000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498551920406,"lastUpdateTimeMillis":1498552211228,"targetState":"outmaintenance","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7228,"jobId":2006249,"deliveryGroupId":584,"machineUid":29,"machineName":"Sheva512RDS03.sheva-qaaws0512.com","initialState":"POWER_ON","currentState":"POWER_OFF","lastTimeMillis":1498552211228,"creationTimestamp":{"hour":8,"minute":25,"second":17,"nano":182000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":30,"second":11,"nano":228000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498551917182,"lastUpdateTimeMillis":1498552211228,"targetState":"POWER_OFF","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7227,"jobId":2006249,"deliveryGroupId":584,"machineUid":33,"machineName":"Sheva512RDS01.sheva-qaaws0512.com","initialState":"POWER_ON","currentState":"POWER_OFF","lastTimeMillis":1498552211225,"creationTimestamp":{"hour":8,"minute":25,"second":17,"nano":22000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":30,"second":11,"nano":225000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498551917022,"lastUpdateTimeMillis":1498552211225,"targetState":"POWER_OFF","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7226,"jobId":2006245,"deliveryGroupId":584,"machineUid":29,"machineName":"Sheva512RDS03.sheva-qaaws0512.com","initialState":"outmaintenance","currentState":"inmaintenance","lastTimeMillis":1498551912764,"creationTimestamp":{"hour":8,"minute":20,"second":41,"nano":837000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":25,"second":12,"nano":764000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498551641837,"lastUpdateTimeMillis":1498551912764,"targetState":"inmaintenance","status":"complete"},{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{},"smartScalingEventId":7225,"jobId":2006245,"deliveryGroupId":584,"machineUid":33,"machineName":"Sheva512RDS01.sheva-qaaws0512.com","initialState":"outmaintenance","currentState":"inmaintenance","lastTimeMillis":1498551912763,"creationTimestamp":{"hour":8,"minute":20,"second":41,"nano":804000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"lastUpdateTimestamp":{"hour":8,"minute":25,"second":12,"nano":763000000,"dayOfYear":178,"dayOfWeek":"TUESDAY","month":"JUNE","dayOfMonth":27,"year":2017,"monthValue":6,"chronology":{"id":"ISO","calendarType":"iso8601"}},"creationTimeMillis":1498551641804,"lastUpdateTimeMillis":1498551912763,"targetState":"inmaintenance","status":"complete"}]
```

## /smartscale/discoverxdsites

### Description

Fetches the discovered xd sites once logged in via CWC or toggling between the tabs .

### URL Structure

`https://SERVERNAME/v0/smartscale/discoverxdsites?access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

Sample response:

```json
{"companyId":40435,"role":"Admin","user":"31873","extraAttrs":{"discoverxdsites":"site already exists for the siteCustomerId :kripaprepiio"}}
```

## /smartscale/{siteId}/infobanner

### Description

Display the info banner for the specified siteId.

### URL Structure

`https://SERVERNAME/v0/smartscale/{siteId}/infobanner?access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

Sample response: true

## /monitor/xdgroupdata

### Description

Displays the monitoring charts based of the deliveryGroup and the siteId opted for the time opted by the user in the history.

### URL Structure

`https://SERVERNAME/v0/monitor/xdgroupdata?deliveryGroupUUID={deliveryGroupUUID}&agentId={agentId}&siteId={siteId}&utilizationSource=user&startTime={startTine}&capacityPerMachine={capacityPerMachine}&access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

Sample response:

```json
{"data":{"92847a2d-9e31-4dd7-a6db-c9ae3965822a":[{"history":[[20.0,1499267628],[20.0,1499268528],[20.0,1499268829],[20.0,1499269128],[20.0,1499269428],[20.0,1499269728],[20.0,1499270029],[20.0,1499270328],[20.0,1499270629],[20.0,1499270928],[20.0,1499271228],[20.0,1499271528],[20.0,1499271828],[20.0,1499272128],[20.0,1499272428],[20.0,1499272728],[20.0,1499272942],[20.0,1499273028],[20.0,1499273328],[20.0,1499273628],[20.0,1499273928],[20.0,1499274229],[20.0,1499274530],[20.0,1499274828],[20.0,1499275128],[20.0,1499275428],[20.0,1499275730],[20.0,1499276028],[20.0,1499276329],[20.0,1499276628],[20.0,1499276930],[20.0,1499277228],[20.0,1499277530],[20.0,1499277828],[20.0,1499278128],[20.0,1499278428],[20.0,1499278728],[20.0,1499279028],[20.0,1499279328],[20.0,1499280529],[20.0,1499280828],[20.0,1499281128],[20.0,1499281428],[20.0,1499281728]],"item":{"taggedKey":"xd.Site.TotalMachinesOnlinePercentage.group[92847a2d-9e31-4dd7-a6db-c9ae3965822a]","shortKey":"TotalMachinesOnlinePercentage","displayName":"TotalMachinesOnlinePercentage"}},{"history":[[5,1499267628],[5,1499268528],[5,1499268829],[5,1499269128],[5,1499269428],[5,1499269728],[5,1499270029],[5,1499270328],[5,1499270629],[5,1499270928],[5,1499271228],[5,1499271528],[5,1499271828],[5,1499272128],[5,1499272428],[5,1499272728],[5,1499272942],[5,1499273028],[5,1499273328],[5,1499273628],[5,1499273928],[5,1499274229],[5,1499274530],[5,1499274828],[5,1499275128],[5,1499275428],[5,1499275730],[5,1499276028],[5,1499276329],[5,1499276628],[5,1499276930],[5,1499277228],[5,1499277530],[5,1499277828],[5,1499278128],[5,1499278428],[5,1499278728],[5,1499279028],[5,1499279328],[5,1499280529],[5,1499280828],[5,1499281128],[5,1499281428],[5,1499281728]],"item":{"taggedKey":"xd.Site.TotalMachines.group[92847a2d-9e31-4dd7-a6db-c9ae3965822a]","shortKey":"TotalMachines","displayName":"TotalMachines"}},{"history":[[33,1499267628],[33,1499268528],[33,1499268829],[33,1499269128],[33,1499269428],[33,1499269728],[33,1499270029],[33,1499270328],[33,1499270629],[33,1499270928],[33,1499271228],[33,1499271528],[33,1499271828],[33,1499272128],[33,1499272428],[33,1499272728],[33,1499272942],[33,1499273028],[33,1499273328],[33,1499273628],[33,1499273928],[33,1499274229],[33,1499274530],[33,1499274828],[33,1499275128],[33,1499275428],[33,1499275730],[33,1499276028],[33,1499276329],[33,1499276628],[33,1499276930],[33,1499277228],[33,1499277530],[33,1499277828],[33,1499278128],[33,1499278428],[33,1499278728],[33,1499279028],[33,1499279328],[33,1499280529],[33,1499280828],[33,1499281128],[33,1499281428],[33,1499281728]],"item":{"taggedKey":"SessionCapacityPercentage","shortKey":"SessionCapacityPercentage","displayName":"SessionCapacityPercentage"}},{"history":[[0,1499267628],[0,1499268528],[0,1499268829],[0,1499269128],[0,1499269428],[0,1499269728],[0,1499270029],[0,1499270328],[0,1499270629],[0,1499270928],[0,1499271228],[0,1499271528],[0,1499271828],[0,1499272128],[0,1499272428],[0,1499272728],[0,1499272942],[0,1499273028],[0,1499273328],[0,1499273628],[0,1499273928],[0,1499274229],[0,1499274530],[0,1499274828],[0,1499275128],[0,1499275428],[0,1499275730],[0,1499276028],[0,1499276329],[0,1499276628],[0,1499276930],[0,1499277228],[0,1499277530],[0,1499277828],[0,1499278128],[0,1499278428],[0,1499278728],[0,1499279028],[0,1499279328],[0,1499280529],[0,1499280828],[0,1499281128],[0,1499281428],[0,1499281728]],"item":{"taggedKey":"xd.Site.TotalMachinesInMaintenance.group[92847a2d-9e31-4dd7-a6db-c9ae3965822a]","shortKey":"TotalMachinesInMaintenance","displayName":"TotalMachinesInMaintenance"}},{"history":[[1,1499267628],[1,1499268528],[1,1499268829],[1,1499269128],[1,1499269428],[1,1499269728],[1,1499270029],[1,1499270328],[1,1499270629],[1,1499270928],[1,1499271228],[1,1499271528],[1,1499271828],[1,1499272128],[1,1499272428],[1,1499272728],[1,1499272942],[1,1499273028],[1,1499273328],[1,1499273628],[1,1499273928],[1,1499274229],[1,1499274530],[1,1499274828],[1,1499275128],[1,1499275428],[1,1499275730],[1,1499276028],[1,1499276329],[1,1499276628],[1,1499276930],[1,1499277228],[1,1499277530],[1,1499277828],[1,1499278128],[1,1499278428],[1,1499278728],[1,1499279028],[1,1499279328],[1,1499280529],[1,1499280828],[1,1499281128],[1,1499281428],[1,1499281728]],"item":{"taggedKey":"xd.Site.TotalCurrentSessions.group[92847a2d-9e31-4dd7-a6db-c9ae3965822a]","shortKey":"TotalCurrentSessions","displayName":"TotalCurrentSessions"}},{"history":[[80.0,1499267628],[80.0,1499268528],[80.0,1499268829],[80.0,1499269128],[80.0,1499269428],[80.0,1499269728],[80.0,1499270029],[80.0,1499270328],[80.0,1499270629],[80.0,1499270928],[80.0,1499271228],[80.0,1499271528],[80.0,1499271828],[80.0,1499272128],[80.0,1499272428],[80.0,1499272728],[80.0,1499272942],[80.0,1499273028],[80.0,1499273328],[80.0,1499273628],[80.0,1499273928],[80.0,1499274229],[80.0,1499274530],[80.0,1499274828],[80.0,1499275128],[80.0,1499275428],[80.0,1499275730],[80.0,1499276028],[80.0,1499276329],[80.0,1499276628],[80.0,1499276930],[80.0,1499277228],[80.0,1499277530],[80.0,1499277828],[80.0,1499278128],[80.0,1499278428],[80.0,1499278728],[80.0,1499279028],[80.0,1499279328],[80.0,1499280529],[80.0,1499280828],[80.0,1499281128],[80.0,1499281428],[80.0,1499281728]],"item":{"taggedKey":"xd.Site.TotalMachinesOfflinePercentage.group[92847a2d-9e31-4dd7-a6db-c9ae3965822a]","shortKey":"TotalMachinesOfflinePercentage","displayName":"TotalMachinesOfflinePercentage"}},{"history":[[1,1499267628],[1,1499268528],[1,1499268829],[1,1499269128],[1,1499269428],[1,1499269728],[1,1499270029],[1,1499270328],[1,1499270629],[1,1499270928],[1,1499271228],[1,1499271528],[1,1499271828],[1,1499272128],[1,1499272428],[1,1499272728],[1,1499272942],[1,1499273028],[1,1499273328],[1,1499273628],[1,1499273928],[1,1499274229],[1,1499274530],[1,1499274828],[1,1499275128],[1,1499275428],[1,1499275730],[1,1499276028],[1,1499276329],[1,1499276628],[1,1499276930],[1,1499277228],[1,1499277530],[1,1499277828],[1,1499278128],[1,1499278428],[1,1499278728],[1,1499279028],[1,1499279328],[1,1499280529],[1,1499280828],[1,1499281128],[1,1499281428],[1,1499281728]],"item":{"taggedKey":"xd.Site.TotalMachinesOnline.group[92847a2d-9e31-4dd7-a6db-c9ae3965822a]","shortKey":"TotalMachinesOnline","displayName":"TotalMachinesOnline"}},{"history":[[40,1499267628],[40,1499268528],[40,1499268829],[40,1499269128],[40,1499269428],[40,1499269728],[40,1499270029],[40,1499270328],[40,1499270629],[40,1499270928],[40,1499271228],[40,1499271528],[40,1499271828],[40,1499272128],[40,1499272428],[40,1499272728],[40,1499272942],[40,1499273028],[40,1499273328],[40,1499273628],[40,1499273928],[40,1499274229],[40,1499274530],[40,1499274828],[40,1499275128],[40,1499275428],[40,1499275730],[40,1499276028],[40,1499276329],[40,1499276628],[40,1499276930],[40,1499277228],[40,1499277530],[40,1499277828],[40,1499278128],[40,1499278428],[40,1499278728],[40,1499279028],[40,1499279328],[40,1499280529],[40,1499280828],[40,1499281128],[40,1499281428],[40,1499281728]],"item":{"taggedKey":"xd.LoadIndexes.group.EffectiveLoadIndex[92847a2d-9e31-4dd7-a6db-c9ae3965822a,avg]","shortKey":"EffectiveLoadIndex","displayName":"EffectiveLoadIndex"}}]},"result":"SUCCESS"}
```

## /monitor/xdsaving

### Description

Get the estimated saving based of the Delivery Group and for the said site for the time opted by the user in the history.

### URL Structure

`https://SERVERNAME/v0/monitor/xdsaving?unit=dollar&deliveryGroupId={deliveryGroupId}&siteId={siteId}&deliveryGroupUUID={deliveryGroupUUID}&agentId={agentId}&startTime={startTime}&endTime={endTime}&access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

Sample response:

```json
{"data":{"92847a2d-9e31-4dd7-a6db-c9ae3965822a":{"avgEstimatedSaving":0.960133311872681,"unit":"dollar","percent":80.0}},"result":"SUCCESS"}
```

## /smartscale/{siteId}/hideinfobanner

### Description

Hide the info banner for the specific siteId

### URL Structure

`https://SERVERNAME/v0/smartscale/{siteId}/hideinfobanner?access_token=VALID_ACCESS_TOKEN`

### Method

POST

### Response

Sample response:

```json
{"companyId":0,"extraAttrs":{},"response":true}
```

## /smartscale/monitoring/{siteId}/{enableMonitorng}/{resumeSmartScaleStatus}

### Description

Turn Smart Scale monitoring on or off. If monitoring is on, control whether or not to resume Smart Scale status of Delivery Groups.

### URL Structure

`https://SERVERNAME/v0/smartscale/monitoring/{siteId}/{enableMonitoring}/{resumeSmartScaleStatus}?access_token=VALID_ACCESS_TOKEN`

### Method

PUT

### Response

Sample response: Returns a success or failure response.

## /smartscale/jobsHealthCheck/{siteId}

### Description

Check the health of the jobs for a specific siteId.

### URL Structure

`https://SERVERNAME/v0/smartscale/jobsHealthCheck/{siteId}?access_token=VALID_ACCESS_TOKEN`

### Method

GET

### Response

Sample response: Returns a success or failure response with the appropriate messaging.