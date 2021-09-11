---
layout: default
title: HMAC Signing             
has_toc: true
nav_order: 2
---

# SmartClean HMAC Signature Version 1

The _Authorization_ header must contain the following values:

`SCHMAC_V1;<access_key>;<signature>`

# Obtaining HMAC credentials

You must have received the HMAC credentials for your property, containing the _accesskey_ and _secretkey_.

Please share the credentials with trusted entities only and ensure the secret is rotated or key inactivated when not in use.

# Signing requests

Each request in Matrix is generally represented as:

`https://console.smartclean.io/api/<module>/<version>/actions?op=<op>&propid=<propid>&pid=<pid>&org=<org>`

|Parameter |Description                                                    |
|:-        |:-                                                             |
|op        |The operation being performed.                                 |
|propid    |The property id.                                               |
|org       |The organisation id.                                           |
|pid       |The building id (send as _scnoop_ if not required).            |
|module    |The module being accessed.                                     |
|version   |The version of API for the module being accessed.              |

Consider a request to be signed at epoch time _1631346630_ for module _attendance_ having op as _scattendance.readIntegration_.

Assuming the access key as _dummyaccesskey/abcd_ (alias _apiuser_) and associated secret key as _mydummysecretkey_ for propert with id _propid_, the signing key for:

`SCHMAC("v1", "attendance", "scattendance.readIntegration", "1631346630", "mydummysecretkey", "propid")`

must be `<module>/<propid>/<op>/<access key>/<epoch time sent in header>` = `attendance/propid/scattendance.readIntegration/dummyaccesskey/abcd/1631346630`

generating the signed value as:

`5f7a71f6ae877c13954c8a70a485ac656bfa5f7cdd1417866660c8e5198d9bf5`

The final value to be sent in _Authorization_ header is then:

`SCHMAC_V1;<access_key>;<signature>` = `SCHMAC_V1;dummyaccesskey/abcd;5f7a71f6ae877c13954c8a70a485ac656bfa5f7cdd1417866660c8e5198d9bf5`

Along with additional headers:

|x-sc-time        |1631346630      |
|x-sc-identity    |apiuser         |
