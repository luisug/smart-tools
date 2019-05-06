---
layout: doc
---
# Authentication API

Citrix Smart Tools uses OAuth2 authentication. The current implementation supports only the client credential profile (i.e., grant_type=client_credentials).

## /acls/encrypt

### Description

Fetches the encrypted token.

### URL Structure

`https://SERVERNAME/v0/acls/encrypt?access_token=VALID_ACCESS_TOKEN`

### Payload

`{PASSWORD}`

### Method

GET

### Response

Encrypted password string

Sample response:

"9BeDKX2P/WTTAxloEj4O6w=="

## /companies

### Description

Retrieves the list of organizations that the client has access.

### URL structure

`httpsː//smart.cloud.com/v0/companies?client_id=APIKey`

### URL example

`httpsː//smart.cloud.com/v0/companies?client_id=YW9s7S5WyT7HebzNeQUB2QasuQ9m9m7%40`

### Method

GET

### Parameters

client_id:_ Mandatory parameter. Specifies the API key associated with a user account.

### Response

List of organizations.

Sample response:

```json
[
   {
      "authorizedToTweetFlag":"N",
      "name":"acme",
      "accountType":"PAID",
      "companyId":40042,
      "oemCode":"SCALEX"
   }
]
```

## /roles

### Description

Retrieves the role associated with the client for the specified organization.

### URL structure

`httpsː//smart.cloud.com/v0/roles?client_id=APIKey&company_id=CompanyId_from_step1

### URL example

`httpsː//smart.cloud.com/v0/roles?client_id=YW9s7S5WyT7HebzNeQUB2QasuQ9m9m7%40&company_id=40042`

### Method

GET

### Parameters

*  `_client_id_`: Mandatory parameter. Specifies the API key associated with a user account.
*  `_company_id_`: Mandatory parameter. Specifies the organization ID of the user. Use the organization ID (companyId) retrieved in Step 1.

### Response

Role associated with the client for the specified organization.

Sample response:

```json
["Admin"]
```

## /oauth/token

### Description

Generates OAuth2 access token. This valid access token is required to be used with Smart Tools REST APIs.

### URL structure

`httpsː//smart.cloud.com/v0/oauth/token?grant_type=client_credentials&scope=Role,CompanyId`

### URL example

`httpsː//smart.cloud.com/v0/oauth/token?grant_type=client_credentials&scope=Admin,40042`

### Method

GET

### Header

Basic authentication Header required.

Header structure:

Authorization: Basic (Base64 encode of (APIkey:SecretKey)). This is part of the OAuth2 specification.

### Parameters

*  `_grant_type_`: Required. Client_credentials are supported.
*  `_scope_`: Required. A comma-separated list of role and companyid.Example:1. Generate Base64 encoded string of APIkey:SecretKey. This is specified as part of the HTTP basic authentication specification.

```curl
curl -H 'Authorization:  Basic cXVIZTNhZGFHZUR5OXlWYVR5WHU5YWp1emFaeVZ5SnUZThhanVt' httpsː//smart.cloud.com/v0/oauth/token?grant_type=client_credentials&scope=Admin,40042
```

Sample response:

```json
{
   "expired":false,
   "tokenType":"bearer",
   "scope":[
      "40042",
      "Admin"
   ],
   "expiration":"Mon Jun 11 05:32:59 UTC 2012",
   "expiresIn":43199,
   "value":"s3hq2n6h07n0nourqepthc",
   "additionalInformation":{}
}
```