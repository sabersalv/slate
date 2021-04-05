---
title: Flood v1.0
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<!-- Generator: Widdershins v4.0.1 -->

<h1 id="flood">Flood v1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="http://localhost:3000">http://localhost:3000</a>

<h1 id="flood-default">Default</h1>

## auth.authenticate

<a id="opIdauth.authenticate"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/auth/authenticate \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/auth/authenticate HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "username": "string",
  "password": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('http://localhost:3000/auth/authenticate',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:3000/auth/authenticate', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/auth/authenticate");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:3000/auth/authenticate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /auth/authenticate`

*Authenticates a user*

> Body parameter

```json
{
  "username": "string",
  "password": "string"
}
```

<h3 id="auth.authenticate-parameters">Parameters</h3>

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

<h3 id="auth.authenticate-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AuthAuthenticationResponse](#schemaauthauthenticationresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Unauthorized|[Error](#schemaerror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity (WebDAV)|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## client.connectionTest

<a id="opIdclient.connectionTest"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/client/connection-test \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/client/connection-test HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/client/connection-test',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/client/connection-test', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/client/connection-test");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/client/connection-test", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /client/connection-test`

*Tests connection to the torrent client*

> Example responses

> 200 Response

```json
{
  "isConnected": true
}
```

<h3 id="client.connectiontest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|Inline|

<h3 id="client.connectiontest-responseschema">Response Schema</h3>

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

## client.settings

<a id="opIdclient.settings"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/client/settings \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/client/settings HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/client/settings',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/client/settings', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/client/settings");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/client/settings", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /client/settings`

*Gets settings of torrent client managed by Flood.*

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

<h3 id="client.settings-responses">Responses</h3>

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

```shell
# You can also use wget
curl -X PATCH http://localhost:3000/client/settings \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH http://localhost:3000/client/settings HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
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
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('http://localhost:3000/client/settings',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:3000/client/settings', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/client/settings");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:3000/client/settings", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

## feeMonitor.get

<a id="opIdfeeMonitor.get"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/feed-monitor \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/feed-monitor HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/feed-monitor',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/feed-monitor', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/feed-monitor");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/feed-monitor", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /feed-monitor`

*Gets subscribed feeds and their automation rules*

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

<h3 id="feemonitor.get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="feemonitor.get-responseschema">Response Schema</h3>

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

## feedMonitor.delete

<a id="opIdfeedMonitor.delete"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:3000/feed-monitor/{id} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:3000/feed-monitor/{id} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/feed-monitor/{id}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','http://localhost:3000/feed-monitor/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/feed-monitor/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:3000/feed-monitor/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /feed-monitor/{id}`

*Deletes feed subscription or automation rule*

<h3 id="feedmonitor.delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="feedmonitor.delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="feedmonitor.delete-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## feedMonitor.getFeed

<a id="opIdfeedMonitor.getFeed"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/feed-monitor/feeds/{id} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/feed-monitor/feeds/{id} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/feed-monitor/feeds/{id}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/feed-monitor/feeds/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/feed-monitor/feeds/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/feed-monitor/feeds/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /feed-monitor/feeds/{id}`

*Gets subscribed feeds*

<h3 id="feedmonitor.getfeed-parameters">Parameters</h3>

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

<h3 id="feedmonitor.getfeed-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="feedmonitor.getfeed-responseschema">Response Schema</h3>

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

## feedMonitor.updateFeedd

<a id="opIdfeedMonitor.updateFeedd"></a>

> Code samples

```shell
# You can also use wget
curl -X PATCH http://localhost:3000/feed-monitor/feeds/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH http://localhost:3000/feed-monitor/feeds/{id} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "type": "feed",
  "_id": "string",
  "label": "string",
  "url": "string",
  "interval": 0,
  "count": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('http://localhost:3000/feed-monitor/feeds/{id}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:3000/feed-monitor/feeds/{id}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/feed-monitor/feeds/{id}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:3000/feed-monitor/feeds/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PATCH /feed-monitor/feeds/{id}`

*Modifies the options of a feed subscription*

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

<h3 id="feedmonitor.updatefeedd-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Feed](#schemafeed)|false|none|
|id|path|string|true|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="feedmonitor.updatefeedd-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="feedmonitor.updatefeedd-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## feedMonitor.addFeed

<a id="opIdfeedMonitor.addFeed"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/feed-monitor/feeds \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:3000/feed-monitor/feeds HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "type": "feed",
  "_id": "string",
  "label": "string",
  "url": "string",
  "interval": 0,
  "count": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('http://localhost:3000/feed-monitor/feeds',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','http://localhost:3000/feed-monitor/feeds', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/feed-monitor/feeds");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:3000/feed-monitor/feeds", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /feed-monitor/feeds`

*Subscribes to a feed*

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

<h3 id="feedmonitor.addfeed-parameters">Parameters</h3>

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

<h3 id="feedmonitor.addfeed-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Feed](#schemafeed)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## feedMonitor.getFeedItems

<a id="opIdfeedMonitor.getFeedItems"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/feed-monitor/feeds/{id}/items \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/feed-monitor/feeds/{id}/items HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/feed-monitor/feeds/{id}/items',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/feed-monitor/feeds/{id}/items', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/feed-monitor/feeds/{id}/items");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/feed-monitor/feeds/{id}/items", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /feed-monitor/feeds/{id}/items`

*Gets items in a feed*

<h3 id="feedmonitor.getfeeditems-parameters">Parameters</h3>

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

<h3 id="feedmonitor.getfeeditems-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="feedmonitor.getfeeditems-responseschema">Response Schema</h3>

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

## feedMonitor.getRules

<a id="opIdfeedMonitor.getRules"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/feed-monitor/rules \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/feed-monitor/rules HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/feed-monitor/rules',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/feed-monitor/rules', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/feed-monitor/rules");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/feed-monitor/rules", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /feed-monitor/rules`

*Gets automation rules*

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

<h3 id="feedmonitor.getrules-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="feedmonitor.getrules-responseschema">Response Schema</h3>

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

## feedMonitor.addRule

<a id="opIdfeedMonitor.addRule"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT http://localhost:3000/feed-monitor/rules \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PUT http://localhost:3000/feed-monitor/rules HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
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
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('http://localhost:3000/feed-monitor/rules',
{
  method: 'PUT',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PUT','http://localhost:3000/feed-monitor/rules', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/feed-monitor/rules");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PUT");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "http://localhost:3000/feed-monitor/rules", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /feed-monitor/rules`

*Adds an automation rule to a feed subscription*

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

<h3 id="feedmonitor.addrule-parameters">Parameters</h3>

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

<h3 id="feedmonitor.addrule-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[Rule](#schemarule)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## get-torrents-hash-contents-indices-data

<a id="opIdget-torrents-hash-contents-indices-data"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/torrents/{hash}/contents/{indices}/data

```

```http
GET http://localhost:3000/torrents/{hash}/contents/{indices}/data HTTP/1.1
Host: localhost:3000

```

```javascript

fetch('http://localhost:3000/torrents/{hash}/contents/{indices}/data',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/torrents/{hash}/contents/{indices}/data', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/torrents/{hash}/contents/{indices}/data");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/torrents/{hash}/contents/{indices}/data", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /torrents/{hash}/contents/{indices}/data`

*Gets downloaded data of contents of a torrent.*

<h3 id="get-torrents-hash-contents-indices-data-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|hash|path|string|true|none|
|indices|path|string|true|none|

<h3 id="get-torrents-hash-contents-indices-data-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="success">
This operation does not require authentication
</aside>

## directoryList

<a id="opIddirectoryList"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/directory-list \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/directory-list HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/directory-list',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/directory-list', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/directory-list");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/directory-list", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /directory-list`

*Lists a directory*

> Example responses

> 200 Response

```json
{}
```

<h3 id="directorylist-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|Forbidden|[Error](#schemaerror)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not Found|[Error](#schemaerror)|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|Unprocessable Entity (WebDAV)|[Error](#schemaerror)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="directorylist-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## getHistory

<a id="opIdgetHistory"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/history \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/history HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/history',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/history', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/history");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/history", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /history`

*Gets transfer history in the given interval*

<h3 id="gethistory-parameters">Parameters</h3>

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

<h3 id="gethistory-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<h3 id="gethistory-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## getNotifications

<a id="opIdgetNotifications"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/notifications?limit=0&start=0 \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/notifications?limit=0&start=0 HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/notifications?limit=0&start=0',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/notifications', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/notifications?limit=0&start=0");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/notifications", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /notifications`

*Gets notifications*

<h3 id="getnotifications-parameters">Parameters</h3>

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

<h3 id="getnotifications-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|

<h3 id="getnotifications-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» notifications|object|false|none|none|
|» count|object|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## deleteNotifications

<a id="opIddeleteNotifications"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:3000/notifications \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:3000/notifications HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/notifications',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','http://localhost:3000/notifications', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/notifications");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:3000/notifications", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /notifications`

*Clears notifications*

> Example responses

> 500 Response

```json
{
  "message": "string",
  "code": 0
}
```

<h3 id="deletenotifications-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## getSettings

<a id="opIdgetSettings"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/settings \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/settings HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/settings',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/settings', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/settings");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/settings", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /settings`

*Gets all Flood's settings*

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

<h3 id="getsettings-responses">Responses</h3>

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

```shell
# You can also use wget
curl -X PATCH http://localhost:3000/settings \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH http://localhost:3000/settings HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
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
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('http://localhost:3000/settings',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:3000/settings', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/settings");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:3000/settings", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

## getSetting

<a id="opIdgetSetting"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/settings/{property} \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/settings/{property} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/settings/{property}',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/settings/{property}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/settings/{property}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/settings/{property}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /settings/{property}`

*Gets Flood's settings*

<h3 id="getsetting-parameters">Parameters</h3>

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

<h3 id="getsetting-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[FloodSettings](#schemafloodsettings)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|Internal Server Error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## auth.register

<a id="opIdauth.register"></a>

> Code samples

```shell
# You can also use wget
curl -X POST http://localhost:3000/auth/register \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST http://localhost:3000/auth/register HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "username": "string",
  "password": "string",
  "client": {},
  "level": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('http://localhost:3000/auth/register',
{
  method: 'POST',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('POST','http://localhost:3000/auth/register', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/auth/register");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("POST");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://localhost:3000/auth/register", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /auth/register`

*Registers a user*

> Body parameter

```json
{
  "username": "string",
  "password": "string",
  "client": {},
  "level": 0
}
```

<h3 id="auth.register-parameters">Parameters</h3>

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

<h3 id="auth.register-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|user is not authorized to create user|string|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|registration is disabled|string|
|422|[Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3)|request validation error|Inline|

<h3 id="auth.register-responseschema">Response Schema</h3>

#### Enumerated Values

|Property|Value|
|---|---|
|level|5|
|level|10|

<aside class="success">
This operation does not require authentication
</aside>

## auth.verify

<a id="opIdauth.verify"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/auth/verify \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/auth/verify HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/auth/verify',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/auth/verify', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/auth/verify");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/auth/verify", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /auth/verify`

*Verifies the connectivity and validity of session*

> Example responses

> 200 Response

```json
{
  "initialUser": true,
  "username": "string",
  "level": 0
}
```

<h3 id="auth.verify-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|[AuthVerificationResponse](#schemaauthverificationresponse)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|not authenticated or token expired|string|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|authenticated succeeded but user is unattached|string|

<aside class="success">
This operation does not require authentication
</aside>

## auth.logout

<a id="opIdauth.logout"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/auth/logout

```

```http
GET http://localhost:3000/auth/logout HTTP/1.1
Host: localhost:3000

```

```javascript

fetch('http://localhost:3000/auth/logout',
{
  method: 'GET'

})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/auth/logout', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/auth/logout");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/auth/logout", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /auth/logout`

*Clears the session cookie*

<h3 id="auth.logout-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|None|

<aside class="success">
This operation does not require authentication
</aside>

## auth.getUsers

<a id="opIdauth.getUsers"></a>

> Code samples

```shell
# You can also use wget
curl -X GET http://localhost:3000/auth/users \
  -H 'Accept: application/json'

```

```http
GET http://localhost:3000/auth/users HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/auth/users',
{
  method: 'GET',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('GET','http://localhost:3000/auth/users', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/auth/users");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("GET");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "http://localhost:3000/auth/users", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /auth/users`

*Lists all users*

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

<h3 id="auth.getusers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|not authenticated or token expired|string|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|user is not authorized to list users|string|

<h3 id="auth.getusers-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» username|string|false|none|none|
|» level|number|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## auth.deleteUser

<a id="opIdauth.deleteUser"></a>

> Code samples

```shell
# You can also use wget
curl -X DELETE http://localhost:3000/auth/users/{username} \
  -H 'Accept: application/json'

```

```http
DELETE http://localhost:3000/auth/users/{username} HTTP/1.1
Host: localhost:3000
Accept: application/json

```

```javascript

const headers = {
  'Accept':'application/json'
};

fetch('http://localhost:3000/auth/users/{username}',
{
  method: 'DELETE',

  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('DELETE','http://localhost:3000/auth/users/{username}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/auth/users/{username}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("DELETE");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("DELETE", "http://localhost:3000/auth/users/{username}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`DELETE /auth/users/{username}`

*Deletes a user*

<h3 id="auth.deleteuser-parameters">Parameters</h3>

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

<h3 id="auth.deleteuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|OK|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|not authenticated or token expired|string|
|403|[Forbidden](https://tools.ietf.org/html/rfc7231#section-6.5.3)|user is not authorized to delete user|string|

<h3 id="auth.deleteuser-responseschema">Response Schema</h3>

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

```shell
# You can also use wget
curl -X PATCH http://localhost:3000/auth/users/{username} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
PATCH http://localhost:3000/auth/users/{username} HTTP/1.1
Host: localhost:3000
Content-Type: application/json
Accept: application/json

```

```javascript
const inputBody = '{
  "username": "string",
  "password": "string",
  "client": {},
  "level": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'
};

fetch('http://localhost:3000/auth/users/{username}',
{
  method: 'PATCH',
  body: inputBody,
  headers: headers
})
.then(function(res) {
    return res.json();
}).then(function(body) {
    console.log(body);
});

```

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

```php
<?php

require 'vendor/autoload.php';

$headers = array(
    'Content-Type' => 'application/json',
    'Accept' => 'application/json',
);

$client = new \GuzzleHttp\Client();

// Define array of request body.
$request_body = array();

try {
    $response = $client->request('PATCH','http://localhost:3000/auth/users/{username}', array(
        'headers' => $headers,
        'json' => $request_body,
       )
    );
    print_r($response->getBody()->getContents());
 }
 catch (\GuzzleHttp\Exception\BadResponseException $e) {
    // handle exception or api errors.
    print_r($e->getMessage());
 }

 // ...

```

```java
URL obj = new URL("http://localhost:3000/auth/users/{username}");
HttpURLConnection con = (HttpURLConnection) obj.openConnection();
con.setRequestMethod("PATCH");
int responseCode = con.getResponseCode();
BufferedReader in = new BufferedReader(
    new InputStreamReader(con.getInputStream()));
String inputLine;
StringBuffer response = new StringBuffer();
while ((inputLine = in.readLine()) != null) {
    response.append(inputLine);
}
in.close();
System.out.println(response.toString());

```

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Content-Type": []string{"application/json"},
        "Accept": []string{"application/json"},
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PATCH", "http://localhost:3000/auth/users/{username}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

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

