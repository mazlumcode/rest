# REST-API

## Table of Contents

1. [Features of REST API](#1---features-of-rest-api)
2. [Methods of REST API](#2---methods-of-rest-api)
3. [HTTP Headers](#3---http-headers)
4. [HTTP Response](#4---http-response)
5. [Authentication Methods](#5---authentication-methods)
6. [Useful Tools](#6---useful-tools)

## 1 - Features of REST API

- Caching
- Client Server Model
- Documentation
- Error Messages
- Layered Architecture
- Stateless
- Uniform Interface

## 2 - Methods of REST API

- CRUD (Create - Read - Update - Delete)

| CLASS METHOD | HTTP METHOD | DESCRIPTION                               |
| ------------ | ----------- | ----------------------------------------- |
| create       | POST        | Create an item within the collection      |
| fetch        | GET         | Retrieve an item                          |
| fetchAll     | GET         | Retrieve all items in the collection      |
| delete       | DELETE      | Delete an item                            |
| deleteAll    | DELETE      | Delete all items in the collection        |
| replaceList  | PUT         | Replace all items in the collection       |
| update       | PUT         | Replace an item                           |
| patch        | PATCH       | Update some fields of an item             |
| -            | HEAD        | Same as GET but no body is returned       |
| -            | OPTIONS     | Information on what methods are supported |

### 2.1 - PATCH vs PUT

```
// Request Payload
{
  address: 'plot 1',
  type: 'duplex',
  color: 'green',
  rooms: '5',
  kitchens: '1',
  windows: 20
}

// Put
{
  address: 'plot 1',
  type: 'duplex',
  color: 'green',
  rooms: '5',
  kitchens: '2',
  windows: 21
}

// Patch
{
  windows: 21
}
```

## 3 - HTTP Headers

## 3.1 - General Headers

| Definition      | Example                                 |
| --------------- | --------------------------------------- |
| Request URL     | https://pokeapi.co/api/v2/pokemon/ditto |
| Request Method  | GET                                     |
| Status Code     | 200                                     |
| Remote Address  | 104.24.125.163:443                      |
| Referrer Policy | no-referrer-when-downgrade              |

## 3.2 - Request Headers

| Definition                | Example                                                                                                                      |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| :authority                | pokeapi.co                                                                                                                   |
| :method                   | GET                                                                                                                          |
| :path                     | /api/v2/pokemon/ditto                                                                                                        |
| :scheme                   | https                                                                                                                        |
| accept                    | text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,_/_;q=0.8 |
| accept-encoding           | gzip, deflate, br                                                                                                            |
| accept-language           | en-US,en;q=0.9,tr;q=0.8                                                                                                      |
| authorization             | Basic dHJhZWZpazpBYmMxmowl                                                                                                   |
| cache-control             | no-cache                                                                                                                     |
| cookie                    | `__cfduid=d7c9cd696f219cad1528c0c890bb432a61597574916`                                                                       |
| pragma                    | no-cache                                                                                                                     |
| sec-fetch-dest            | document                                                                                                                     |
| sec-fetch-mode            | navigate                                                                                                                     |
| sec-fetch-site            | none                                                                                                                         |
| sec-fetch-user            | ?1                                                                                                                           |
| upgrade-insecure-requests | 1                                                                                                                            |
| user-agent                | Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_6) ...    |

## 3.3 - Response Headers

| Definition                  | Example                                                                                 |
| --------------------------- | --------------------------------------------------------------------------------------- |
| access-control-allow-origin | `*`                                                                                     |
| age                         | 31528                                                                                   |
| cache-control               | public, max-age=86400, s-maxage=86400                                                   |
| cf-cache-status             | HIT                                                                                     |
| cf-ray                      | 5c4f127648dfffc0-WAW                                                                    |
| cf-request-id               | 04a549ddec0000ffc068bf1200000001                                                        |
| content-encoding            | br                                                                                      |
| content-language            | en-US                                                                                   |
| content-length              | 200                                                                                     |
| content-type                | application/json; charset=utf-8                                                         |
| date                        | Tue, 18 Aug 2020 22:29:10 GMT                                                           |
| etag                        | W/"4eb8-H7z57sSwXJ3okX8Z5xag8Ebo4DY"                                                    |
| expect-ct                   | max-age=604800, report-uri="https://report-uri.cloudflare.com/cdn-cgi/beacon/expect-ct" |
| function-execution-id       | c25kmnk8rcht                                                                            |
| server                      | cloudflare                                                                              |
| status                      | 200                                                                                     |
| vary                        | Accept-Encoding,cookie,need-authorization, x-fh-requested-host, accept-encoding         |
| x-cache                     | MISS                                                                                    |
| x-cache-hits                | 0                                                                                       |
| x-cloud-trace-context       | 75a3e1160a06401ce775562fc5434b94;o=1                                                    |
| x-country-code              | PL                                                                                      |
| x-orig-accept-language      | pl-PL,pl;q=0.9,en-US;q=0.8,en;q=0.7                                                     |
| x-powered-by                | Express                                                                                 |
| x-served-by                 | cache-cph20648-CPH                                                                      |
| x-timer                     | S1597583948.368771,VS0,VE618                                                            |

## 4 - HTTP Response

## 4.1 - Response Content Types

| APPLICATION                       | AUDIO      | IMAGE      | MULTIPART             | TEXT            | VIDEO      |
| --------------------------------- | ---------- | ---------- | --------------------- | --------------- | ---------- |
| application/json                  | audio/mpeg | image/gif  | multipart/mixed       | text/css        | video/mpeg |
| application/pdf                   | -          | image/jpeg | multipart/alternative | text/csv        | video/mp4  |
| application/x-www-form-urlencoded | -          | image/svg  | multipart/form-data   | text/html       | -          |
| application/xhtml+xml             | -          | -          | -                     | text/javascript | -          |
| application/xml                   | -          | -          | -                     | text/plain      | -          |
| application/zip                   | -          | -          | -                     | text/xml        | -          |

## 4.2 - HTTP Response Status Codes

| INFORMATIONAL RESPONSE    | SUCCESS                             | REDIRECTION              | CLIENT ERRORS                              | SERVER ERRORS                  |
| ------------------------- | ----------------------------------- | ------------------------ | ------------------------------------------ | ------------------------------ |
| 100 (Continue)            | 200 (OK)                            | 300 (Multiple Choices)   | 400 (Bad Request)                          | 500 (Internal Server Error)    |
| 101 (Switching Protocols) | 201 (Created)                       | 301 (Moved Permanently)  | 401 (Unauthorized)                         | 501 (Not Implemented)          |
| 102 (Processing)          | 202 (Accepted)                      | 302 (Found)              | 402 (Payment Required)                     | 502 (Bad Gateway)              |
| -                         | 203 (Non-Authoritative Information) | 303 (See Other)          | 403 (Forbidden)                            | 503 (Service Unavailable)      |
| -                         | 204 (No Content)                    | 304 (Not Modified)       | 404 (Not Found)                            | 504 (Gateway Timeout)          |
| -                         | 205 (Reset Content)                 | 305 (Use Proxy)          | 405 (Method Not Allowed)                   | 505 (HTTP Version Not Support) |
| -                         | 206 (Partial Content)               | 306 (Switch Proxy)       | 406 (Not Acceptable)                       | 506 (Variant Also Negotiates)  |
| -                         | 207 (Multi-Status)                  | 307 (Temporary Redirect) | 407 (Proxy Authentication Required)        | 507 (Insufficient Storage)     |
| -                         | 208 (Already Reported)              | 308 (Permanent Redirect) | 408 (Request Timeout)                      | 509 (Bandwidth Limit Exceeded) |
| -                         | 226 (IM Used)                       | -                        | 409 (Conflict)                             | 510 (Not Extended)             |
| -                         | -                                   | -                        | 410 (Gone)                                 | -                              |
| -                         | -                                   | -                        | 411 (Length Required)                      | -                              |
| -                         | -                                   | -                        | 412 (Precondition Failed)                  | -                              |
| -                         | -                                   | -                        | 413 (Request Entity Too Large)             | -                              |
| -                         | -                                   | -                        | 414 (Request-URI Too Long)                 | -                              |
| -                         | -                                   | -                        | 415 (Unsupported Media Type)               | -                              |
| -                         | -                                   | -                        | 416 (Requested Range Not Satisfiable)      | -                              |
| -                         | -                                   | -                        | 417 (Expectation Failed)                   | -                              |
| -                         | -                                   | -                        | 418 (Im a teapot)                          | -                              |
| -                         | -                                   | -                        | 420 (Enhance Your Calm)                    | -                              |
| -                         | -                                   | -                        | 422 (Unprocessable Entity)                 | -                              |
| -                         | -                                   | -                        | 423 (Locked)                               | -                              |
| -                         | -                                   | -                        | 424 (Failed Dependency)                    | -                              |
| -                         | -                                   | -                        | 425 (Unordered Collection)                 | -                              |
| -                         | -                                   | -                        | 426 (Upgrade Required)                     | -                              |
| -                         | -                                   | -                        | 428 (Precondition Required)                | -                              |
| -                         | -                                   | -                        | 429 (Too Many Requests)                    | -                              |
| -                         | -                                   | -                        | 431 (Request Header Fields Too Large)      | -                              |
| -                         | -                                   | -                        | 444 (No Response)                          | -                              |
| -                         | -                                   | -                        | 449 (Retry With)                           | -                              |
| -                         | -                                   | -                        | 450 (Blocked by Windows Parental Controls) | -                              |
| -                         | -                                   | -                        | 499 (Client Closed Request)                | -                              |

## 5 - Authentication Methods

| Definition                      |
| ------------------------------- |
| Basic                           |
| Bearer                          |
| Digest                          |
| OAuth 1.0 (Digest Scheme)       |
| OAuth 2.0 (Bearer Token Scheme) |
| Hawk Authentication             |
| AWS Signature                   |
| Local API Key                   |
| OpenID Connect                  |

## 6 - Useful Tools

| Definition        | Type                  |
| ----------------- | --------------------- |
| Passport (npm)    | Authentication        |
| RAML              | Design API            |
| Pipedream         | Mocking               |
| Httpbin           | Mocking               |
| json-server (npm) | Mocking               |
| JSONPlaceholder   | Testing               |
| jsonwebtoken.io   | Encode or Decode JWTs |
| jwt.io            | Encode or Decode JWTs |
| loremipsum.io     | Text Placeholders     |
| picsum.photos     | Image Placeholders    |
| helmet            | Security              |
