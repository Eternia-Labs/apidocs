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

|Parameter |Description|
|:-        |:-:        |                 
|op        |           |
|propid    |           |         
|pid       |           |  
