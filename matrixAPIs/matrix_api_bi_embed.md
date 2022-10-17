---
layout: default
title: Matrix BI API
parent: Matrix API offerings
grand_parent: SmartClean Matrix API Docs
has_children: false
nav_order: 4
---

# Matrix Embeddable BI dashboards
This API allows you to get links to BI dashboards.

---
## Request: Get Signed URL to BI dashboard

### Complete Endpoint:

POST
`https://console.smartclean.io/_gapi/apis/apis.smartclean.bi/v1/actions?op=api.getSignedEmbeddedURI
&propid=<Property ID>&pid=<Building ID>`

Where,
- **Method:** `POST`

- **Base URL:** `https://console.smartclean.io`

- **Path:** `/_gapi/apis/apis.smartclean.bi/v1/actions`

- **Query String:** `?op=api.getSignedEmbeddedURI&propid=<Property ID>&pid=<Building ID>`

### Parameters in query string:
1. Text in the URL after "?" character is the query string that contains parameters to pass to the request.
2. Set the operation name (_"op"_ as "_api.getSignedEmbeddedURI_")
   1. i.e., `op=api.getSignedEmbeddedURI`
   2. This is a constant, for our service to identify the request.
3. The following are variable query parameters, that you must specify:
   1. `propid=<Property ID>`: ID of your SmartClean enabled Property
   2. `pid=<Project ID>`: ID of Building (Project) within your SmartClean enabled Property

### Headers:

| Key | Value | Description |
| --- | ------|-------------|
| `Authorization` | (Required) Your SmartClean Access Token | Basic Auth / Access Token / SC-HMAC-V4 Signature (based on authentication type)|
| `x-sc-auth` | (Optional) Your SmartClean Application ID | If you have registered your application with us for federated access|

### Body:
```json
{
    "Dashboard": 1  
}
```
Where value of attribute: "Dashboard" is a valid ID of the dashboard or widget


### Example Request:

#### URL:

`https://console.smartclean.io/_gapi/apis/apis.smartclean.bi/v1/actions?op=api.getSignedEmbeddedURI&propid=d2ff1cc0ee104abba3a8ba030c72cd06&pid=45ea1d38775046dbbdc955362b8834b1`

Where,
following are values of the variable query parameters:
1. `propid=d2ff1cc0ee104abba3a8ba030c72cd06`
2. `pid=45ea1d38775046dbbdc955362b8834b1`

#### Body:
```json
{
    "Dashboard": 3  
}
```


#### Response Body:

```json
{
    "ExpiresAt": 1664009192,
    "URI": "aHR0cHM6Ly9yZWFsc2Vuc2UubWV0YWJhc2VhcHAuY29tL2VtYmVkL2Rhc2hib2FyZC9leUpoYkdjaU9pSklVekkxTmlJc0luUjVjQ0k2SWtwWFZDSjkuZXlKbGVIQWlPakUyTmpRd01Ea3hPVElzSW1saGRDSTZNVFkyTkRBd09ESTVNaXdpY0dGeVlXMXpJanA3SW5CcFpDSTZJalExWldFeFpETTROemMxTURRMlpHSmlaR001TlRVek5qSmlPRGd6TkdJeElpd2ljSEp2Y0dsa0lqb2laREptWmpGall6QmxaVEV3TkdGaVltRXpZVGhpWVRBek1HTTNNbU5rTURZaWZTd2ljbVZ6YjNWeVkyVWlPbnNpWkdGemFHSnZZWEprSWpvemZYMC42OTl1d1I0bHV3ME9oMzUzWXlNd2IyWnh4S1JkNGFFVlExZElJTDVjSnF3I3RoZW1lPW5pZ2h0JmJvcmRlcmVkPXRydWUmdGl0bGVkPXRydWU="
}
```

Where value of the following attributes represent:
1. "ExpiresAt": Time at which this URI (link) expires
   1. This is an epoch timestamp (seconds)
2. "URI": Base 64 encoded string of the web link to the dashboard.
   1. Copy this value to open the dashboard, as described below in the "Outcome"


### Outcome:

Once you have the Base 64 encoded string of the dashboard link,
You can get the final URL to use in a browser by either the following ways:

1. Paste the copied value of URI, by replacing "<base 64 string>" in the following URL:
`https://www.smartclean.io/matrix/bi/embedded/v1/indexv2.html?_loc=<base64 string>&_w=100%25&_h=1024`

2. Decode the copied value of URI using base 64 encoding scheme.  
