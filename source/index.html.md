---
title: Flood v1.0
language_tabs:
  - ruby: Ruby
  - python: Python
language_clients:
  - ruby: ""
  - python: ""
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="flood">Flood v1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="http://localhost:3000">http://localhost:3000</a>

<h1 id="flood-default">Default</h1>

## Authenticates a user

<a id="opIdauth.authenticate"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:3000/auth/authenticate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:3000/auth/authenticate', headers = headers)

print(r.json())

```

`POST /auth/authenticate`

> Body parameter

```json
{
  "username": "string",
  "password": "string"
}
```

<h3 id="authenticates-a-user-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AuthAuthenticationOptions](#schemaauthauthenticationoptions)|false|none|

> Example responses

> 401 Response

```json
{
  "message": "string",
  "code": 0
}
```

<h3 id="authenticates-a-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AuthAuthenticationResponse](#schemaauthauthenticationresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[Error](#schemaerror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity (WebDAV)|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## Tests connection to the torrent client

<a id="opIdclient.connectionTest"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/client/connection-test',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/client/connection-test', headers = headers)

print(r.json())

```

`GET /client/connection-test`

> Example responses

> 200 Response

```json
{
  "isConnected": true
}
```

<h3 id="tests-connection-to-the-torrent-client-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|Inline|

<h3 id="tests-connection-to-the-torrent-client-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» isConnected|boolean|false|none|none|

Status Code **500**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» isConnected|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Gets settings of torrent client managed by Flood.

<a id="opIdclient.settings"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/client/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/client/settings', headers = headers)

print(r.json())

```

`GET /client/settings`

> Example responses

> 200 Response

```json
{
  "dht": true,
  "dhtPort": 0,
  "directoryDefault": "string",
  "networkHttpMaxOpen": 0,
  "networkLocalAddress": [
    "string"
  ],
  "networkMaxOpenFiles": 0,
  "networkPortOpen": true,
  "networkPortRandom": true,
  "networkPortRange": "string",
  "piecesHashOnCompletion": true,
  "piecesMemoryMax": 0,
  "protocolPex": true,
  "throttleGlobalDownSpeed": 0,
  "throttleGlobalUpSpeed": 0,
  "throttleMaxPeersNormal": 0,
  "throttleMaxPeersSeed": 0,
  "throttleMaxDownloads": 0,
  "throttleMaxDownloadsGlobal": 0,
  "throttleMaxUploads": 0,
  "throttleMaxUploadsGlobal": 0,
  "throttleMinPeersNormal": 0,
  "throttleMinPeersSeed": 0,
  "trackersNumWant": 0
}
```

<h3 id="gets-settings-of-torrent-client-managed-by-flood.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[ClientSettings](#schemaclientsettings)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## client.updateSettings

<a id="opIdclient.updateSettings"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.patch 'http://localhost:3000/client/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('http://localhost:3000/client/settings', headers = headers)

print(r.json())

```

`PATCH /client/settings`

> Body parameter

```json
{
  "dht": true,
  "dhtPort": 0,
  "directoryDefault": "string",
  "networkHttpMaxOpen": 0,
  "networkLocalAddress": [
    "string"
  ],
  "networkMaxOpenFiles": 0,
  "networkPortOpen": true,
  "networkPortRandom": true,
  "networkPortRange": "string",
  "piecesHashOnCompletion": true,
  "piecesMemoryMax": 0,
  "protocolPex": true,
  "throttleGlobalDownSpeed": 0,
  "throttleGlobalUpSpeed": 0,
  "throttleMaxPeersNormal": 0,
  "throttleMaxPeersSeed": 0,
  "throttleMaxDownloads": 0,
  "throttleMaxDownloadsGlobal": 0,
  "throttleMaxUploads": 0,
  "throttleMaxUploadsGlobal": 0,
  "throttleMinPeersNormal": 0,
  "throttleMinPeersSeed": 0,
  "trackersNumWant": 0
}
```

<h3 id="client.updatesettings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ClientSettings](#schemaclientsettings)|false|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="client.updatesettings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="client.updatesettings-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## Gets subscribed feeds and their automation rules

<a id="opIdfeeMonitor.get"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/feed-monitor',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/feed-monitor', headers = headers)

print(r.json())

```

`GET /feed-monitor`

> Example responses

> 200 Response

```json
{
  "feeds": [
    {
      "type": "feed",
      "_id": "string",
      "label": "string",
      "url": "string",
      "interval": 0,
      "count": 0
    }
  ],
  "rules": [
    {
      "type": "rule",
      "_id": "string",
      "label": "string",
      "feedIDs": [
        "string"
      ],
      "field": "string",
      "match": "string",
      "exclude": "string",
      "destination": "string",
      "tags": [
        "string"
      ],
      "startOnLoad": true,
      "isBasePath": true,
      "count": 0
    }
  ]
}
```

<h3 id="gets-subscribed-feeds-and-their-automation-rules-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="gets-subscribed-feeds-and-their-automation-rules-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» feeds|[[Feed](#schemafeed)]|false|none|none|
|»» Feed|[Feed](#schemafeed)|false|none|none|
|»»» type|string|false|none|none|
|»»» _id|string|false|none|none|
|»»» label|string|false|none|none|
|»»» url|string|false|none|none|
|»»» interval|number|false|none|none|
|»»» count|number|false|none|none|
|» rules|[[Rule](#schemarule)]|false|none|none|
|»» Rule|[Rule](#schemarule)|false|none|none|
|»»» type|string|false|none|none|
|»»» _id|string|false|none|none|
|»»» label|string|false|none|none|
|»»» feedIDs|[string]|false|none|none|
|»»» field|string|false|none|none|
|»»» match|string|false|none|none|
|»»» exclude|string|false|none|none|
|»»» destination|string|false|none|none|
|»»» tags|[string]|false|none|none|
|»»» startOnLoad|boolean|false|none|none|
|»»» isBasePath|boolean|false|none|none|
|»»» count|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|feed|
|type|rule|

<aside class="success">
This operation does not require authentication
</aside>

## Deletes feed subscription or automation rule

<a id="opIdfeedMonitor.delete"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:3000/feed-monitor/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:3000/feed-monitor/{id}', headers = headers)

print(r.json())

```

`DELETE /feed-monitor/{id}`

<h3 id="deletes-feed-subscription-or-automation-rule-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="deletes-feed-subscription-or-automation-rule-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="deletes-feed-subscription-or-automation-rule-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## Gets subscribed feeds

<a id="opIdfeedMonitor.getFeed"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/feed-monitor/feeds/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/feed-monitor/feeds/{id}', headers = headers)

print(r.json())

```

`GET /feed-monitor/feeds/{id}`

<h3 id="gets-subscribed-feeds-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "type": "feed",
    "_id": "string",
    "label": "string",
    "url": "string",
    "interval": 0,
    "count": 0
  }
]
```

<h3 id="gets-subscribed-feeds-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="gets-subscribed-feeds-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Feed](#schemafeed)]|false|none|none|
|» Feed|[Feed](#schemafeed)|false|none|none|
|»» type|string|false|none|none|
|»» _id|string|false|none|none|
|»» label|string|false|none|none|
|»» url|string|false|none|none|
|»» interval|number|false|none|none|
|»» count|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|feed|

<aside class="success">
This operation does not require authentication
</aside>

## Modifies the options of a feed subscription

<a id="opIdfeedMonitor.updateFeedd"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.patch 'http://localhost:3000/feed-monitor/feeds/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('http://localhost:3000/feed-monitor/feeds/{id}', headers = headers)

print(r.json())

```

`PATCH /feed-monitor/feeds/{id}`

> Body parameter

```json
{
  "type": "feed",
  "_id": "string",
  "label": "string",
  "url": "string",
  "interval": 0,
  "count": 0
}
```

<h3 id="modifies-the-options-of-a-feed-subscription-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Feed](#schemafeed)|false|none|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="modifies-the-options-of-a-feed-subscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="modifies-the-options-of-a-feed-subscription-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## Subscribes to a feed

<a id="opIdfeedMonitor.addFeed"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:3000/feed-monitor/feeds',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:3000/feed-monitor/feeds', headers = headers)

print(r.json())

```

`PUT /feed-monitor/feeds`

> Body parameter

```json
{
  "type": "feed",
  "_id": "string",
  "label": "string",
  "url": "string",
  "interval": 0,
  "count": 0
}
```

```xml
<?xml version="1.0" encoding="UTF-8" ?>
<Feed>
  <type>feed</type>
  <_id>string</_id>
  <label>string</label>
  <url>string</url>
  <interval>0</interval>
  <count>0</count>
</Feed>
```

<h3 id="subscribes-to-a-feed-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Feed](#schemafeed)|false|none|

> Example responses

> 200 Response

```json
{
  "type": "feed",
  "_id": "string",
  "label": "string",
  "url": "string",
  "interval": 0,
  "count": 0
}
```

<h3 id="subscribes-to-a-feed-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Feed](#schemafeed)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## Gets items in a feed

<a id="opIdfeedMonitor.getFeedItems"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/feed-monitor/feeds/{id}/items',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/feed-monitor/feeds/{id}/items', headers = headers)

print(r.json())

```

`GET /feed-monitor/feeds/{id}/items`

<h3 id="gets-items-in-a-feed-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|search|query|string|false|none|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
[
  {
    "title": "string",
    "urls": [
      "string"
    ]
  }
]
```

<h3 id="gets-items-in-a-feed-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="gets-items-in-a-feed-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Item](#schemaitem)]|false|none|none|
|» Item|[Item](#schemaitem)|false|none|none|
|»» title|string|false|none|none|
|»» urls|[string]|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Gets automation rules

<a id="opIdfeedMonitor.getRules"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/feed-monitor/rules',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/feed-monitor/rules', headers = headers)

print(r.json())

```

`GET /feed-monitor/rules`

> Example responses

> 200 Response

```json
[
  {
    "type": "rule",
    "_id": "string",
    "label": "string",
    "feedIDs": [
      "string"
    ],
    "field": "string",
    "match": "string",
    "exclude": "string",
    "destination": "string",
    "tags": [
      "string"
    ],
    "startOnLoad": true,
    "isBasePath": true,
    "count": 0
  }
]
```

<h3 id="gets-automation-rules-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="gets-automation-rules-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Rule](#schemarule)]|false|none|none|
|» Rule|[Rule](#schemarule)|false|none|none|
|»» type|string|false|none|none|
|»» _id|string|false|none|none|
|»» label|string|false|none|none|
|»» feedIDs|[string]|false|none|none|
|»» field|string|false|none|none|
|»» match|string|false|none|none|
|»» exclude|string|false|none|none|
|»» destination|string|false|none|none|
|»» tags|[string]|false|none|none|
|»» startOnLoad|boolean|false|none|none|
|»» isBasePath|boolean|false|none|none|
|»» count|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|rule|

<aside class="success">
This operation does not require authentication
</aside>

## Adds an automation rule to a feed subscription

<a id="opIdfeedMonitor.addRule"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.put 'http://localhost:3000/feed-monitor/rules',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.put('http://localhost:3000/feed-monitor/rules', headers = headers)

print(r.json())

```

`PUT /feed-monitor/rules`

> Body parameter

```json
{
  "type": "rule",
  "_id": "string",
  "label": "string",
  "feedIDs": [
    "string"
  ],
  "field": "string",
  "match": "string",
  "exclude": "string",
  "destination": "string",
  "tags": [
    "string"
  ],
  "startOnLoad": true,
  "isBasePath": true,
  "count": 0
}
```

<h3 id="adds-an-automation-rule-to-a-feed-subscription-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Rule](#schemarule)|false|none|

> Example responses

> 200 Response

```json
{
  "type": "rule",
  "_id": "string",
  "label": "string",
  "feedIDs": [
    "string"
  ],
  "field": "string",
  "match": "string",
  "exclude": "string",
  "destination": "string",
  "tags": [
    "string"
  ],
  "startOnLoad": true,
  "isBasePath": true,
  "count": 0
}
```

<h3 id="adds-an-automation-rule-to-a-feed-subscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Rule](#schemarule)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## Gets downloaded data of contents of a torrent.

<a id="opIdget-torrents-hash-contents-indices-data"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

result = RestClient.get 'http://localhost:3000/torrents/{hash}/contents/{indices}/data',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('http://localhost:3000/torrents/{hash}/contents/{indices}/data')

print(r.json())

```

`GET /torrents/{hash}/contents/{indices}/data`

<h3 id="gets-downloaded-data-of-contents-of-a-torrent.-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|none|
|indices|path|string|true|none|

<h3 id="gets-downloaded-data-of-contents-of-a-torrent.-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="success">
This operation does not require authentication
</aside>

## Lists a directory

<a id="opIddirectoryList"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/directory-list',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/directory-list', headers = headers)

print(r.json())

```

`GET /directory-list`

> Example responses

> 200 Response

```json
{}
```

<h3 id="lists-a-directory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[Error](#schemaerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[Error](#schemaerror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity (WebDAV)|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="lists-a-directory-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## Gets transfer history in the given interval

<a id="opIdgetHistory"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/history',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/history', headers = headers)

print(r.json())

```

`GET /history`

<h3 id="gets-transfer-history-in-the-given-interval-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|snapshot|query|string|false|none|

#### Enumerated Values

|Parameter|Value|
|---|---|
|snapshot|FIVE_MINUTE|
|snapshot|THIRTY_MINUTE|
|snapshot|HOUR|
|snapshot|DAY|
|snapshot|WEEK|
|snapshot|MONTH|
|snapshot|YEAR|

> Example responses

> 200 Response

```json
{}
```

<h3 id="gets-transfer-history-in-the-given-interval-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="gets-transfer-history-in-the-given-interval-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## Gets notifications

<a id="opIdgetNotifications"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/notifications',
  params: {
  'limit' => 'number',
'start' => 'number'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/notifications', params={
  'limit': '0',  'start': '0'
}, headers = headers)

print(r.json())

```

`GET /notifications`

<h3 id="gets-notifications-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|query|string|false|none|
|limit|query|number|true|none|
|start|query|number|true|none|
|allNotifications|query|boolean|false|none|

> Example responses

> 200 Response

```json
{
  "notifications": {},
  "count": {}
}
```

<h3 id="gets-notifications-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="gets-notifications-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» notifications|object|false|none|none|
|» count|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Clears notifications

<a id="opIddeleteNotifications"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:3000/notifications',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:3000/notifications', headers = headers)

print(r.json())

```

`DELETE /notifications`

> Example responses

> 500 Response

```json
{
  "message": "string",
  "code": 0
}
```

<h3 id="clears-notifications-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## Gets all Flood's settings

<a id="opIdgetSettings"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/settings', headers = headers)

print(r.json())

```

`GET /settings`

> Example responses

> 200 Response

```json
{
  "language": "string",
  "sortTorrents": {
    "direction": "desc",
    "property": {}
  },
  "torrentListColumns": [
    {}
  ],
  "torrentListColumnWidths": {},
  "torrentContextMenuActions": [
    {}
  ],
  "torrentListViewSize": "condensed",
  "speedLimits": {
    "download": [
      0
    ],
    "upload": [
      0
    ]
  },
  "mountPoints": [
    "string"
  ],
  "deleteTorrentData": true,
  "startTorrentsOnLoad": true,
  "torrentDestinations": [
    "string"
  ],
  "UITagSelectorMode": "single",
  "UITorrentsAddTab": "by-url"
}
```

<h3 id="gets-all-flood's-settings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[FloodSettings](#schemafloodsettings)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## updateSettings

<a id="opIdupdateSettings"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.patch 'http://localhost:3000/settings',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('http://localhost:3000/settings', headers = headers)

print(r.json())

```

`PATCH /settings`

> Body parameter

```json
{
  "language": "string",
  "sortTorrents": {
    "direction": "desc",
    "property": {}
  },
  "torrentListColumns": [
    {}
  ],
  "torrentListColumnWidths": {},
  "torrentContextMenuActions": [
    {}
  ],
  "torrentListViewSize": "condensed",
  "speedLimits": {
    "download": [
      0
    ],
    "upload": [
      0
    ]
  },
  "mountPoints": [
    "string"
  ],
  "deleteTorrentData": true,
  "startTorrentsOnLoad": true,
  "torrentDestinations": [
    "string"
  ],
  "UITagSelectorMode": "single",
  "UITorrentsAddTab": "by-url"
}
```

<h3 id="updatesettings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[FloodSettings](#schemafloodsettings)|false|none|

> Example responses

> 200 Response

```json
{
  "language": "string",
  "sortTorrents": {
    "direction": "desc",
    "property": {}
  },
  "torrentListColumns": [
    {}
  ],
  "torrentListColumnWidths": {},
  "torrentContextMenuActions": [
    {}
  ],
  "torrentListViewSize": "condensed",
  "speedLimits": {
    "download": [
      0
    ],
    "upload": [
      0
    ]
  },
  "mountPoints": [
    "string"
  ],
  "deleteTorrentData": true,
  "startTorrentsOnLoad": true,
  "torrentDestinations": [
    "string"
  ],
  "UITagSelectorMode": "single",
  "UITorrentsAddTab": "by-url"
}
```

<h3 id="updatesettings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[FloodSettings](#schemafloodsettings)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## Gets Flood's settings

<a id="opIdgetSetting"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/settings/{property}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/settings/{property}', headers = headers)

print(r.json())

```

`GET /settings/{property}`

<h3 id="gets-flood's-settings-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|property|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "language": "string",
  "sortTorrents": {
    "direction": "desc",
    "property": {}
  },
  "torrentListColumns": [
    {}
  ],
  "torrentListColumnWidths": {},
  "torrentContextMenuActions": [
    {}
  ],
  "torrentListViewSize": "condensed",
  "speedLimits": {
    "download": [
      0
    ],
    "upload": [
      0
    ]
  },
  "mountPoints": [
    "string"
  ],
  "deleteTorrentData": true,
  "startTorrentsOnLoad": true,
  "torrentDestinations": [
    "string"
  ],
  "UITagSelectorMode": "single",
  "UITorrentsAddTab": "by-url"
}
```

<h3 id="gets-flood's-settings-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[FloodSettings](#schemafloodsettings)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## Registers a user

<a id="opIdauth.register"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.post 'http://localhost:3000/auth/register',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('http://localhost:3000/auth/register', headers = headers)

print(r.json())

```

`POST /auth/register`

> Body parameter

```json
{
  "username": "string",
  "password": "string",
  "client": {},
  "level": 0
}
```

<h3 id="registers-a-user-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|cookie|query|boolean|false|whether to Set-Cookie if succeeded|
|body|body|[AuthRegistrationOptions](#schemaauthregistrationoptions)|false|none|

> Example responses

> 200 Response

```json
{
  "username": "string"
}
```

<h3 id="registers-a-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|user is not authorized to create user|string|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|registration is disabled|string|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|request validation error|Inline|

<h3 id="registers-a-user-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|level|5|
|level|10|

<aside class="success">
This operation does not require authentication
</aside>

## Verifies the connectivity and validity of session

<a id="opIdauth.verify"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/auth/verify',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/auth/verify', headers = headers)

print(r.json())

```

`GET /auth/verify`

> Example responses

> 200 Response

```json
{
  "initialUser": true,
  "username": "string",
  "level": 0
}
```

<h3 id="verifies-the-connectivity-and-validity-of-session-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AuthVerificationResponse](#schemaauthverificationresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|not authenticated or token expired|string|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|authenticated succeeded but user is unattached|string|

<aside class="success">
This operation does not require authentication
</aside>

## Clears the session cookie

<a id="opIdauth.logout"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

result = RestClient.get 'http://localhost:3000/auth/logout',
  params: {
  }

p JSON.parse(result)

```

```python
import requests

r = requests.get('http://localhost:3000/auth/logout')

print(r.json())

```

`GET /auth/logout`

<h3 id="clears-the-session-cookie-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="success">
This operation does not require authentication
</aside>

## Lists all users

<a id="opIdauth.getUsers"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get 'http://localhost:3000/auth/users',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('http://localhost:3000/auth/users', headers = headers)

print(r.json())

```

`GET /auth/users`

> Example responses

> 200 Response

```json
[
  {
    "username": "string",
    "level": 0
  }
]
```

<h3 id="lists-all-users-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|not authenticated or token expired|string|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|user is not authorized to list users|string|

<h3 id="lists-all-users-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» username|string|false|none|none|
|» level|number|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Deletes a user

<a id="opIdauth.deleteUser"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete 'http://localhost:3000/auth/users/{username}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('http://localhost:3000/auth/users/{username}', headers = headers)

print(r.json())

```

`DELETE /auth/users/{username}`

<h3 id="deletes-a-user-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|username|path|string|true|none|

> Example responses

> 200 Response

```json
{
  "username": "string"
}
```

<h3 id="deletes-a-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|not authenticated or token expired|string|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|user is not authorized to delete user|string|

<h3 id="deletes-a-user-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» username|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## auth.updateUser

<a id="opIdauth.updateUser"></a>

> Code samples

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json'
}

result = RestClient.patch 'http://localhost:3000/auth/users/{username}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.patch('http://localhost:3000/auth/users/{username}', headers = headers)

print(r.json())

```

`PATCH /auth/users/{username}`

> Body parameter

```json
{
  "username": "string",
  "password": "string",
  "client": {},
  "level": 0
}
```

<h3 id="auth.updateuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[AuthRegistrationOptions](#schemaauthregistrationoptions)|false|none|
|username|path|string|true|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="auth.updateuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|not authenticated or token expired|string|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|user is not authorized to update user|string|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|request validation error|[Error](#schemaerror)|

<h3 id="auth.updateuser-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocS_Error">Error</h2>
<!-- backwards compatibility -->
<a id="schemaerror"></a>
<a id="schema_Error"></a>
<a id="tocSerror"></a>
<a id="tocserror"></a>

```json
{
  "message": "string",
  "code": 0
}

```

Error

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|code|number|false|none|none|

<h2 id="tocS_ClientSettings">ClientSettings</h2>
<!-- backwards compatibility -->
<a id="schemaclientsettings"></a>
<a id="schema_ClientSettings"></a>
<a id="tocSclientsettings"></a>
<a id="tocsclientsettings"></a>

```json
{
  "dht": true,
  "dhtPort": 0,
  "directoryDefault": "string",
  "networkHttpMaxOpen": 0,
  "networkLocalAddress": [
    "string"
  ],
  "networkMaxOpenFiles": 0,
  "networkPortOpen": true,
  "networkPortRandom": true,
  "networkPortRange": "string",
  "piecesHashOnCompletion": true,
  "piecesMemoryMax": 0,
  "protocolPex": true,
  "throttleGlobalDownSpeed": 0,
  "throttleGlobalUpSpeed": 0,
  "throttleMaxPeersNormal": 0,
  "throttleMaxPeersSeed": 0,
  "throttleMaxDownloads": 0,
  "throttleMaxDownloadsGlobal": 0,
  "throttleMaxUploads": 0,
  "throttleMaxUploadsGlobal": 0,
  "throttleMinPeersNormal": 0,
  "throttleMinPeersSeed": 0,
  "trackersNumWant": 0
}

```

ClientSettings

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|dht|boolean|false|none|none|
|dhtPort|number|false|none|none|
|directoryDefault|string|false|none|none|
|networkHttpMaxOpen|number|false|none|none|
|networkLocalAddress|[string]|false|none|none|
|networkMaxOpenFiles|number|false|none|none|
|networkPortOpen|boolean|false|none|none|
|networkPortRandom|boolean|false|none|none|
|networkPortRange|string|false|none|none|
|piecesHashOnCompletion|boolean|false|none|none|
|piecesMemoryMax|number|false|none|none|
|protocolPex|boolean|false|none|none|
|throttleGlobalDownSpeed|number|false|none|none|
|throttleGlobalUpSpeed|number|false|none|none|
|throttleMaxPeersNormal|number|false|none|none|
|throttleMaxPeersSeed|number|false|none|none|
|throttleMaxDownloads|number|false|none|none|
|throttleMaxDownloadsGlobal|number|false|none|none|
|throttleMaxUploads|number|false|none|none|
|throttleMaxUploadsGlobal|number|false|none|none|
|throttleMinPeersNormal|number|false|none|none|
|throttleMinPeersSeed|number|false|none|none|
|trackersNumWant|number|false|none|none|

<h2 id="tocS_Feed">Feed</h2>
<!-- backwards compatibility -->
<a id="schemafeed"></a>
<a id="schema_Feed"></a>
<a id="tocSfeed"></a>
<a id="tocsfeed"></a>

```json
{
  "type": "feed",
  "_id": "string",
  "label": "string",
  "url": "string",
  "interval": 0,
  "count": 0
}

```

Feed

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|_id|string|false|none|none|
|label|string|false|none|none|
|url|string|false|none|none|
|interval|number|false|none|none|
|count|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|feed|

<h2 id="tocS_Rule">Rule</h2>
<!-- backwards compatibility -->
<a id="schemarule"></a>
<a id="schema_Rule"></a>
<a id="tocSrule"></a>
<a id="tocsrule"></a>

```json
{
  "type": "rule",
  "_id": "string",
  "label": "string",
  "feedIDs": [
    "string"
  ],
  "field": "string",
  "match": "string",
  "exclude": "string",
  "destination": "string",
  "tags": [
    "string"
  ],
  "startOnLoad": true,
  "isBasePath": true,
  "count": 0
}

```

Rule

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|_id|string|false|none|none|
|label|string|false|none|none|
|feedIDs|[string]|false|none|none|
|field|string|false|none|none|
|match|string|false|none|none|
|exclude|string|false|none|none|
|destination|string|false|none|none|
|tags|[string]|false|none|none|
|startOnLoad|boolean|false|none|none|
|isBasePath|boolean|false|none|none|
|count|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|rule|

<h2 id="tocS_Item">Item</h2>
<!-- backwards compatibility -->
<a id="schemaitem"></a>
<a id="schema_Item"></a>
<a id="tocSitem"></a>
<a id="tocsitem"></a>

```json
{
  "title": "string",
  "urls": [
    "string"
  ]
}

```

Item

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|title|string|false|none|none|
|urls|[string]|false|none|none|

<h2 id="tocS_FloodSettings">FloodSettings</h2>
<!-- backwards compatibility -->
<a id="schemafloodsettings"></a>
<a id="schema_FloodSettings"></a>
<a id="tocSfloodsettings"></a>
<a id="tocsfloodsettings"></a>

```json
{
  "language": "string",
  "sortTorrents": {
    "direction": "desc",
    "property": {}
  },
  "torrentListColumns": [
    {}
  ],
  "torrentListColumnWidths": {},
  "torrentContextMenuActions": [
    {}
  ],
  "torrentListViewSize": "condensed",
  "speedLimits": {
    "download": [
      0
    ],
    "upload": [
      0
    ]
  },
  "mountPoints": [
    "string"
  ],
  "deleteTorrentData": true,
  "startTorrentsOnLoad": true,
  "torrentDestinations": [
    "string"
  ],
  "UITagSelectorMode": "single",
  "UITorrentsAddTab": "by-url"
}

```

FloodSettings

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|language|string|false|none|none|
|sortTorrents|object|false|none|none|
|» direction|string|false|none|none|
|» property|object|false|none|none|
|torrentListColumns|[object]|false|none|none|
|torrentListColumnWidths|object|false|none|none|
|torrentContextMenuActions|[object]|false|none|none|
|torrentListViewSize|string|false|none|none|
|speedLimits|object|false|none|none|
|» download|[number]|false|none|none|
|» upload|[number]|false|none|none|
|mountPoints|[string]|false|none|none|
|deleteTorrentData|boolean|false|none|none|
|startTorrentsOnLoad|boolean|false|none|none|
|torrentDestinations|[string]|false|none|none|
|UITagSelectorMode|string|false|none|none|
|UITorrentsAddTab|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|direction|desc|
|direction|asc|
|torrentListViewSize|condensed|
|torrentListViewSize|expanded|
|UITagSelectorMode|single|
|UITagSelectorMode|multi|
|UITorrentsAddTab|by-url|
|UITorrentsAddTab|by-file|
|UITorrentsAddTab|by-creation|

<h2 id="tocS_AuthAuthenticationOptions">AuthAuthenticationOptions</h2>
<!-- backwards compatibility -->
<a id="schemaauthauthenticationoptions"></a>
<a id="schema_AuthAuthenticationOptions"></a>
<a id="tocSauthauthenticationoptions"></a>
<a id="tocsauthauthenticationoptions"></a>

```json
{
  "username": "string",
  "password": "string"
}

```

AuthAuthenticationOptions

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|true|none|none|
|password|string|true|none|none|

<h2 id="tocS_AuthAuthenticationResponse">AuthAuthenticationResponse</h2>
<!-- backwards compatibility -->
<a id="schemaauthauthenticationresponse"></a>
<a id="schema_AuthAuthenticationResponse"></a>
<a id="tocSauthauthenticationresponse"></a>
<a id="tocsauthauthenticationresponse"></a>

```json
{
  "success": true,
  "username": "string",
  "level": 5
}

```

AuthAuthenticationResponse

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|boolean|false|none|none|
|username|string|false|none|none|
|level|number|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|level|5|
|level|10|

<h2 id="tocS_AuthRegistrationOptions">AuthRegistrationOptions</h2>
<!-- backwards compatibility -->
<a id="schemaauthregistrationoptions"></a>
<a id="schema_AuthRegistrationOptions"></a>
<a id="tocSauthregistrationoptions"></a>
<a id="tocsauthregistrationoptions"></a>

```json
{
  "username": "string",
  "password": "string",
  "client": {},
  "level": 0
}

```

AuthRegistrationOptions

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|username|string|false|none|none|
|password|string|false|none|none|
|client|object|false|none|none|
|level|number|false|none|none|

<h2 id="tocS_AuthVerificationResponse">AuthVerificationResponse</h2>
<!-- backwards compatibility -->
<a id="schemaauthverificationresponse"></a>
<a id="schema_AuthVerificationResponse"></a>
<a id="tocSauthverificationresponse"></a>
<a id="tocsauthverificationresponse"></a>

```json
{
  "initialUser": true,
  "username": "string",
  "level": 0
}

```

AuthVerificationResponse

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|initialUser|boolean|false|none|none|
|username|string|false|none|none|
|level|number|false|none|none|

