---
layout: doc
---
# API Overview

REST APIs allow you to retrieve and collect useful system information from Citrix Smart Tools database. You can also perform some basic management functions using the REST APIs.

The global URL to access any API is `httpsː//SERVERNAME/SUPPORTED_VERSION/`. The server name will change depending on the environment. Current supported version is v0\. For example, `https://smart.cloud.com/v0/`.

By default, every string passed to and from is UTF-8 encoded. Some of them are Base64 encoded. Each API explicitly specifies which field is base64 encoded.

Before you access any API, ensure that you have the apikey and apisecret key. The client can not use same username and password used to access the Citrix Smart Tools UI. You can interchange apikey and secret key also as _client_id_ and _client_secret_ for OAuth2 authentication purposes. After successful authentication every API must have a parameter _access_token_, which contains a VALID_TOKEN_GENERATED_BY_AUTHENTICATION.

The system will respond with an HTTP error code, if an invalid or incorrect API is passed. The following table describes some of the HTTP status error codes:

| Error Code | Description | Resolution |
| --- | --- | --- |
| 400 | Bad input parameters or error messages. | Ensure correct input parameters are provided. |
| 401 | Bad credentials or expired token.  | Ensure valid authentication credentials are used. |
| 404 | Bad API name.  | Ensure the correct API is passed. |
| 500 | Internal server error. This happens only if errors are not handled properly on the server.  | Ensure errors are properly handled at the internal server. |