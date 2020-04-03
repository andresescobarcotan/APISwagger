---
title: Rakam API Documentation
language_tabs:
  - java: Java
  - go: Go
  - javascript: JavaScript
toc_footers: []
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="rakam-api-documentation">Rakam API Documentation v1.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

An analytics platform API that lets you create your own analytics services.

Base URLs:

* <a href="//https://app.getrakam.com/">//https://app.getrakam.com/</a>

Email: <a href="mailto:contact@rakam.com">Support</a> 
License: <a href="http://www.apache.org/licenses/LICENSE-2.0.html">Apache License 2.0</a>

# Authentication

* API Key (ui_read_key)
    - Parameter Name: **undefined**, in: header. 

* API Key (read_key)
    - Parameter Name: **read_key**, in: header. 

* API Key (ui_master_key)
    - Parameter Name: **undefined**, in: header. 

* API Key (master_key)
    - Parameter Name: **master_key**, in: header. 

* API Key (write_key)
    - Parameter Name: **undefined**, in: header. 

<h1 id="rakam-api-documentation-event-stream">event-stream</h1>

Event Stream Module

<a href="https://getrakam.com/doc">Rakam Documentation</a>

## subscribe

<a id="opIdsubscribe"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/stream/subscribe");
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
    req, err := http.NewRequest("GET", "/https://app.getrakam.com/stream/subscribe", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript

$.ajax({
  url: '/https://app.getrakam.com/stream/subscribe',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /stream/subscribe`

*Subscribe Event Stream*

Subscribes the event stream periodically to the client.

<h3 id="subscribe-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="rakam-api-documentation-funnel">funnel</h1>

Funnel Analyzer module

<a href="https://getrakam.com/doc">Rakam Documentation</a>

## analyze

<a id="opIdanalyze"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/funnel/analyze");
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
        "Content-Type": []string{"application/json"},
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/https://app.getrakam.com/funnel/analyze", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/funnel/analyze',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /funnel/analyze`

*Execute query*

> Body parameter

```json
{
  "project": "string",
  "steps": [
    {
      "collection": "string",
      "filterExpression": "string"
    }
  ],
  "dimension": "string",
  "startDate": "2020-04-03",
  "endDate": "2020-04-03",
  "enableOtherGrouping": true
}
```

<h3 id="analyze-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[FunnelQuery](#schemafunnelquery)|true|none|

<h3 id="analyze-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|successful operation|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

<h1 id="rakam-api-documentation-retention">retention</h1>

Retention Analyzer module

<a href="https://getrakam.com/doc">Rakam Documentation</a>

## execute

<a id="opIdexecute"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/retention/analyze");
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
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/https://app.getrakam.com/retention/analyze", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/retention/analyze',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /retention/analyze`

*Execute query*

<h3 id="execute-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|successful operation|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

<h1 id="rakam-api-documentation-user">user</h1>

User module for Rakam

<a href="https://getrakam.com/doc">Rakam Documentation</a>

## create

<a id="opIdcreate"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/user/create");
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
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/user/create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/user/create',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /user/create`

*Create new user*

> Body parameter

```json
{
  "project": "string",
  "properties": {
    "property1": {},
    "property2": {}
  }
}
```

<h3 id="create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserHttpService_create](#schemauserhttpservice_create)|true|none|

> Example responses

> 200 Response

```json
{
  "identifier": {}
}
```

<h3 id="create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[CreateUserResponse](#schemacreateuserresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<aside class="success">
This operation does not require authentication
</aside>

## getUser

<a id="opIdgetUser"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/user/get");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/user/get", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/user/get',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /user/get`

*Get user*

> Body parameter

```yaml
project: string
user: string

```

<h3 id="getuser-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» project|body|string|false|none|
|» user|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "project": "string",
  "id": {},
  "properties": {
    "property1": {},
    "property2": {}
  }
}
```

<h3 id="getuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[User](#schemauser)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|User does not exist.|None|

<aside class="success">
This operation does not require authentication
</aside>

## getEvents

<a id="opIdgetEvents"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/user/get_events");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/user/get_events", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/user/get_events',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /user/get_events`

*Get events of the user*

> Body parameter

```yaml
project: string
user: string
limit: 0
offset: 0

```

<h3 id="getevents-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» project|body|string|false|none|
|» user|body|string|false|none|
|» limit|body|integer(int32)|false|none|
|» offset|body|integer(int64)|false|none|

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="getevents-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|User does not exist.|None|

<h3 id="getevents-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## metadata

<a id="opIdmetadata"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/user/metadata");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/user/metadata", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/user/metadata',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /user/metadata`

*Get user storage metadata*

> Body parameter

```yaml
project: string

```

<h3 id="metadata-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listQueries](#schemalistqueries)|false|none|
|» project|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "columns": [
    {
      "name": "string",
      "type": "STRING",
      "nullable": false,
      "unique": false,
      "descriptiveName": "string",
      "description": "string",
      "category": "string"
    }
  ],
  "identifierColumn": "string"
}
```

<h3 id="metadata-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[MetadataResponse](#schemametadataresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<aside class="success">
This operation does not require authentication
</aside>

## search

<a id="opIdsearch"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/user/search");
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
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/user/search", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/user/search',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /user/search`

*Search users*

> Body parameter

```json
{
  "project": "string",
  "filter": "string",
  "event_filters": [
    {
      "collection": "string",
      "aggregation": {
        "field": "string",
        "minimum": 0,
        "maximum": 0,
        "type": "COUNT"
      },
      "filterExpression": "string"
    }
  ],
  "sorting": {
    "column": "string",
    "order": "asc"
  },
  "offset": 0,
  "limit": 0
}
```

<h3 id="search-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[UserHttpService_search](#schemauserhttpservice_search)|true|none|

> Example responses

> 200 Response

```json
{
  "metadata": [
    {
      "name": "string",
      "type": "STRING",
      "nullable": false,
      "unique": false,
      "descriptiveName": "string",
      "description": "string",
      "category": "string"
    }
  ],
  "result": [
    [
      {}
    ]
  ],
  "error": {
    "message": "string",
    "sqlState": "string",
    "errorCode": 0
  },
  "properties": {
    "property1": {},
    "property2": {}
  },
  "failed": false
}
```

<h3 id="search-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[QueryResult](#schemaqueryresult)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<aside class="success">
This operation does not require authentication
</aside>

## setUserProperty

<a id="opIdsetUserProperty"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/user/set_property");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/user/set_property", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/user/set_property',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /user/set_property`

*Set user property*

> Body parameter

```yaml
project: string
user: string
property: string
value: string

```

<h3 id="setuserproperty-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» project|body|string|false|none|
|» user|body|string|false|none|
|» property|body|string|false|none|
|» value|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "success": false,
  "message": "string"
}
```

<h3 id="setuserproperty-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[JsonResponse](#schemajsonresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|User does not exist.|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="rakam-api-documentation-user-mailbox">user-mailbox</h1>

<a href="https://getrakam.com/doc">Rakam Documentation</a>

## get

<a id="opIdget"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/user/mailbox/get");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/user/mailbox/get", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/user/mailbox/get',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /user/mailbox/get`

*Get user mailbox*

Returns the last mails sent to the user

> Body parameter

```yaml
project: string
user: string
parent: 0
limit: 0
offset: 0

```

<h3 id="get-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» project|body|string|false|none|
|» user|body|string|false|none|
|» parent|body|integer(int32)|false|none|
|» limit|body|integer(int32)|false|none|
|» offset|body|integer(int64)|false|none|

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "content": "string",
    "from_user": {},
    "to_user": {},
    "parentId": 0,
    "seen": false,
    "time": 0,
    "project": "string"
  }
]
```

<h3 id="get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User does not exist.|None|

<h3 id="get-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Message](#schemamessage)]|false|none|none|
|» id|integer(int32)|false|none|none|
|» content|string|false|none|none|
|» from_user|object|false|none|none|
|» to_user|object|false|none|none|
|» parentId|integer(int32)|false|none|none|
|» seen|boolean|false|none|none|
|» time|integer(int64)|false|none|none|
|» project|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

## getConnectedUsers

<a id="opIdgetConnectedUsers"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/user/mailbox/getOnlineUsers");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/user/mailbox/getOnlineUsers", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/user/mailbox/getOnlineUsers',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /user/mailbox/getOnlineUsers`

*Get connected users*

> Body parameter

```yaml
project: string

```

<h3 id="getconnectedusers-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listQueries](#schemalistqueries)|false|none|
|» project|body|string|false|none|

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="getconnectedusers-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<h3 id="getconnectedusers-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

## listen

<a id="opIdlisten"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/user/mailbox/listen");
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
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/https://app.getrakam.com/user/mailbox/listen", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/user/mailbox/listen',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /user/mailbox/listen`

*Listen all mailboxes*

<h3 id="listen-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|project|query|string|false|none|

<h3 id="listen-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|default|Default|successful operation|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

## markAsRead

<a id="opIdmarkAsRead"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/user/mailbox/mark_as_read");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "undefined": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/user/mailbox/mark_as_read", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'undefined':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/user/mailbox/mark_as_read',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /user/mailbox/mark_as_read`

*Mark mail as read*

Marks the specified mails as read.

> Body parameter

```yaml
project: string
user: string
message_ids:
  - 0

```

<h3 id="markasread-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» project|body|string|false|none|
|» user|body|string|false|none|
|» message_ids|body|[integer]|false|none|

> Example responses

> 200 Response

```json
{
  "success": false,
  "message": "string"
}
```

<h3 id="markasread-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[JsonResponse](#schemajsonresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User does not exist.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
write_key
</aside>

## send

<a id="opIdsend"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/user/mailbox/send");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "undefined": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/user/mailbox/send", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'undefined':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/user/mailbox/send',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /user/mailbox/send`

*Send mail to user*

Sends a mail to users mailbox

> Body parameter

```yaml
project: string
from_user: string
to_user: string
parent: 0
message: string
timestamp: 0

```

<h3 id="send-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» project|body|string|false|none|
|» from_user|body|string|false|none|
|» to_user|body|string|false|none|
|» parent|body|integer(int32)|false|none|
|» message|body|string|false|none|
|» timestamp|body|integer(int64)|false|none|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "content": "string",
  "from_user": {},
  "to_user": {},
  "parentId": 0,
  "seen": false,
  "time": 0,
  "project": "string"
}
```

<h3 id="send-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[Message](#schemamessage)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|User does not exist.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
write_key
</aside>

<h1 id="rakam-api-documentation-realtime">realtime</h1>

<a href="https://getrakam.com/doc">Rakam Documentation</a>

## create

<a id="opIdcreate"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/realtime/create");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/realtime/create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/realtime/create',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /realtime/create`

*Create report*

> Body parameter

```yaml
project: string
name: string
chart: string
collections:
  - string
aggregation: string
table_name: string
filter: string
measure: string
dimension: string

```

<h3 id="create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» project|body|string|false|none|
|» name|body|string|false|none|
|» chart|body|string|false|none|
|» collections|body|[string]|false|none|
|» aggregation|body|string|false|none|
|» table_name|body|string|false|none|
|» filter|body|string|false|none|
|» measure|body|string|false|none|
|» dimension|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "success": false,
  "message": "string"
}
```

<h3 id="create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[JsonResponse](#schemajsonresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

## delete

<a id="opIddelete"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/realtime/delete");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/realtime/delete", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/realtime/delete',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /realtime/delete`

*Delete report*

> Body parameter

```yaml
project: string
name: string

```

<h3 id="delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[delete](#schemadelete)|false|none|
|» project|body|string|false|none|
|» name|body|string|false|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="delete-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

## get

<a id="opIdget"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/realtime/get");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/realtime/get", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/realtime/get',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /realtime/get`

*Get report*

> Body parameter

```yaml
project: string
table_name: string
filter: string
aggregate: true
date_start: '2020-04-03T11:17:15Z'
date_end: '2020-04-03T11:17:15Z'

```

<h3 id="get-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» project|body|string|false|none|
|» table_name|body|string|false|none|
|» filter|body|string|false|none|
|» aggregate|body|boolean|false|none|
|» date_start|body|string(date-time)|false|none|
|» date_end|body|string(date-time)|false|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Report does not exist.|None|

<h3 id="get-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

## listReports

<a id="opIdlistReports"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/realtime/list");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/realtime/list", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/realtime/list',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /realtime/list`

*List reports*

> Body parameter

```yaml
project: string

```

<h3 id="listreports-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listQueries](#schemalistqueries)|false|none|
|» project|body|string|false|none|

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="listreports-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="listreports-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

<h1 id="rakam-api-documentation-admin">admin</h1>

System related actions

<a href="https://getrakam.com/doc">Rakam Documentation</a>

## getModules

<a id="opIdgetModules"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/admin/modules");
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
        "master_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/https://app.getrakam.com/admin/modules", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'master_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/admin/modules',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /admin/modules`

*List installed modules*

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="getmodules-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="getmodules-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
master_key
</aside>

<h1 id="rakam-api-documentation-event">event</h1>

Event Analyzer

<a href="https://getrakam.com/doc">Rakam Documentation</a>

## collect

<a id="opIdcollect"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/event/collect");
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
        "undefined": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/event/collect", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'undefined':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/event/collect',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /event/collect`

*Collect event*

> Body parameter

```json
{
  "project": "",
  "collection": "",
  "properties": {}
}
```

<h3 id="collect-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[org.rakam.collection.event.EventCollectionHttpService.collect](#schemaorg.rakam.collection.event.eventcollectionhttpservice.collect)|false|none|

<h3 id="collect-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
write_key
</aside>

## execute

<a id="opIdexecute"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/query/execute");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/query/execute", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/query/execute',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /query/execute`

*Analyze events*

> Body parameter

```yaml
project: string
query: string
limit: 0

```

<h3 id="execute-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[execute](#schemaexecute)|false|none|
|» project|body|string|false|none|
|» query|body|string|false|none|
|» limit|body|integer(int32)|false|none|

> Example responses

> 200 Response

```json
{
  "metadata": [
    {
      "name": "string",
      "type": "STRING",
      "nullable": false,
      "unique": false,
      "descriptiveName": "string",
      "description": "string",
      "category": "string"
    }
  ],
  "result": [
    [
      {}
    ]
  ],
  "error": {
    "message": "string",
    "sqlState": "string",
    "errorCode": 0
  },
  "properties": {
    "property1": {},
    "property2": {}
  },
  "failed": false
}
```

<h3 id="execute-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[QueryResult](#schemaqueryresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

<h1 id="rakam-api-documentation-materialized-view">materialized-view</h1>

Materialized view

<a href="https://getrakam.com/doc">Rakam Documentation</a>

## create

<a id="opIdcreate"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/materialized-view/create");
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
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/materialized-view/create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/materialized-view/create',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /materialized-view/create`

*Create view*

> Body parameter

```json
{
  "project": "string",
  "name": "string",
  "table_name": "string",
  "query": "string",
  "update_interval": "string",
  "options": {
    "property1": {},
    "property2": {}
  }
}
```

<h3 id="create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[MaterializedView](#schemamaterializedview)|true|none|

> Example responses

> 200 Response

```json
{
  "success": false,
  "message": "string"
}
```

<h3 id="create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[JsonResponse](#schemajsonresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<aside class="success">
This operation does not require authentication
</aside>

## delete

<a id="opIddelete"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/materialized-view/delete");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/materialized-view/delete", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/materialized-view/delete',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /materialized-view/delete`

*Delete materialized view*

> Body parameter

```yaml
project: string
name: string

```

<h3 id="delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[delete](#schemadelete)|false|none|
|» project|body|string|false|none|
|» name|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "success": false,
  "message": "string"
}
```

<h3 id="delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[JsonResponse](#schemajsonresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<aside class="success">
This operation does not require authentication
</aside>

## get

<a id="opIdget"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/materialized-view/get");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/materialized-view/get", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/materialized-view/get',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /materialized-view/get`

*Get view*

> Body parameter

```yaml
project: string
name: string

```

<h3 id="get-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[delete](#schemadelete)|false|none|
|» project|body|string|false|none|
|» name|body|string|false|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="get-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<h3 id="get-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## listViews

<a id="opIdlistViews"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/materialized-view/list");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/materialized-view/list", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/materialized-view/list',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /materialized-view/list`

*List views*

> Body parameter

```yaml
project: string

```

<h3 id="listviews-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listQueries](#schemalistqueries)|false|none|
|» project|body|string|false|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="listviews-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<h3 id="listviews-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## schema

<a id="opIdschema"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/materialized-view/schema");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/materialized-view/schema", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/materialized-view/schema',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /materialized-view/schema`

*Get schemas*

> Body parameter

```yaml
project: string

```

<h3 id="schema-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listQueries](#schemalistqueries)|false|none|
|» project|body|string|false|none|

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="schema-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<h3 id="schema-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## update

<a id="opIdupdate"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/materialized-view/update");
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
    req, err := http.NewRequest("GET", "/https://app.getrakam.com/materialized-view/update", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript

$.ajax({
  url: '/https://app.getrakam.com/materialized-view/update',
  method: 'get',

  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /materialized-view/update`

*Update view*

<h3 id="update-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="rakam-api-documentation-continuous-query">continuous-query</h1>

Continuous query

<a href="https://getrakam.com/doc">Rakam Documentation</a>

## create

<a id="opIdcreate"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/continuous-query/create");
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
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/continuous-query/create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/continuous-query/create',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /continuous-query/create`

*Create stream*

> Body parameter

```json
{
  "project": "string",
  "name": "string",
  "query": "string",
  "table_name": "string",
  "collections": [
    "string"
  ],
  "partition_keys": [
    "string"
  ],
  "options": {
    "property1": {},
    "property2": {}
  }
}
```

<h3 id="create-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[ContinuousQuery](#schemacontinuousquery)|true|none|

> Example responses

> 200 Response

```json
{
  "success": false,
  "message": "string"
}
```

<h3 id="create-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[JsonResponse](#schemajsonresponse)|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<aside class="success">
This operation does not require authentication
</aside>

## delete

<a id="opIddelete"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/continuous-query/delete");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/continuous-query/delete", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/continuous-query/delete',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /continuous-query/delete`

*Delete stream*

> Body parameter

```yaml
project: string
name: string

```

<h3 id="delete-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[delete](#schemadelete)|false|none|
|» project|body|string|false|none|
|» name|body|string|false|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="delete-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<h3 id="delete-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## listQueries

<a id="opIdlistQueries"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/continuous-query/list");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/continuous-query/list", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/continuous-query/list',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /continuous-query/list`

*List queries*

> Body parameter

```yaml
project: string

```

<h3 id="listqueries-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listQueries](#schemalistqueries)|false|none|
|» project|body|string|false|none|

> Example responses

> 200 Response

```json
{}
```

<h3 id="listqueries-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<h3 id="listqueries-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

## schema

<a id="opIdschema"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/continuous-query/schema");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/continuous-query/schema", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json'

};

$.ajax({
  url: '/https://app.getrakam.com/continuous-query/schema',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /continuous-query/schema`

*Get query schema*

> Body parameter

```yaml
project: string

```

<h3 id="schema-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listQueries](#schemalistqueries)|false|none|
|» project|body|string|false|none|

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="schema-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<h3 id="schema-responseschema">Response Schema</h3>

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="rakam-api-documentation-event-explorer">event-explorer</h1>

## execute

<a id="opIdexecute"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/event-explorer/analyze");
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
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/event-explorer/analyze", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/event-explorer/analyze',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /event-explorer/analyze`

*Perform simple query on event data*

> Body parameter

```json
{
  "project": "string",
  "measure": {
    "column": "string",
    "aggregation": "COUNT"
  },
  "grouping": {
    "type": "COLUMN",
    "value": "string"
  },
  "segment": {
    "type": "COLUMN",
    "value": "string"
  },
  "filterExpression": "string",
  "startDate": "2020-04-03",
  "endDate": "2020-04-03",
  "collections": [
    "string"
  ]
}
```

<h3 id="execute-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[EventExplorerHttpService_execute](#schemaeventexplorerhttpservice_execute)|true|none|

> Example responses

> 200 Response

```json
{
  "metadata": [
    {
      "name": "string",
      "type": "STRING",
      "nullable": false,
      "unique": false,
      "descriptiveName": "string",
      "description": "string",
      "category": "string"
    }
  ],
  "result": [
    [
      {}
    ]
  ],
  "error": {
    "message": "string",
    "sqlState": "string",
    "errorCode": 0
  },
  "properties": {
    "property1": {},
    "property2": {}
  },
  "failed": false
}
```

<h3 id="execute-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[QueryResult](#schemaqueryresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

## getEventDimensions

<a id="opIdgetEventDimensions"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/event-explorer/event_dimensions");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/event-explorer/event_dimensions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/event-explorer/event_dimensions',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /event-explorer/event_dimensions`

*Event statistics*

> Body parameter

```yaml
project: string

```

<h3 id="geteventdimensions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listQueries](#schemalistqueries)|false|none|
|» project|body|string|false|none|

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="geteventdimensions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="geteventdimensions-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

## getExtraDimensions

<a id="opIdgetExtraDimensions"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/event-explorer/extra_dimensions");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/event-explorer/extra_dimensions", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/event-explorer/extra_dimensions',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /event-explorer/extra_dimensions`

*Event statistics*

> Body parameter

```yaml
project: string

```

<h3 id="getextradimensions-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listQueries](#schemalistqueries)|false|none|
|» project|body|string|false|none|

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="getextradimensions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="getextradimensions-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

## getEventStatistics

<a id="opIdgetEventStatistics"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/event-explorer/statistics");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "read_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/event-explorer/statistics", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'read_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/event-explorer/statistics',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /event-explorer/statistics`

*Event statistics*

> Body parameter

```yaml
project: string
dimension: string
startDate: '2020-04-03'
endDate: '2020-04-03'

```

<h3 id="geteventstatistics-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» project|body|string|false|none|
|» dimension|body|string|false|none|
|» startDate|body|string(date)|false|none|
|» endDate|body|string(date)|false|none|

> Example responses

> 200 Response

```json
{
  "metadata": [
    {
      "name": "string",
      "type": "STRING",
      "nullable": false,
      "unique": false,
      "descriptiveName": "string",
      "description": "string",
      "category": "string"
    }
  ],
  "result": [
    [
      {}
    ]
  ],
  "error": {
    "message": "string",
    "sqlState": "string",
    "errorCode": 0
  },
  "properties": {
    "property1": {},
    "property2": {}
  },
  "failed": false
}
```

<h3 id="geteventstatistics-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[QueryResult](#schemaqueryresult)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
read_key
</aside>

<h1 id="rakam-api-documentation-project">project</h1>

## createProject

<a id="opIdcreateProject"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/project/create");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "master_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/project/create", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'master_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/project/create',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /project/create`

*Create project*

> Body parameter

```yaml
name: string

```

<h3 id="createproject-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» name|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "success": false,
  "message": "string"
}
```

<h3 id="createproject-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|[JsonResponse](#schemajsonresponse)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
master_key
</aside>

## getProjects

<a id="opIdgetProjects"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/project/list");
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
        "master_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/https://app.getrakam.com/project/list", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json',
  'master_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/project/list',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /project/list`

*List created projects*

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="getprojects-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|

<h3 id="getprojects-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
master_key
</aside>

## schema

<a id="opIdschema"></a>

> Code samples

```java
URL obj = new URL("/https://app.getrakam.com/project/schema");
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
        "Content-Type": []string{"application/x-www-form-urlencoded"},
        "Accept": []string{"application/json"},
        "master_key": []string{"API_KEY"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/https://app.getrakam.com/project/schema", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Content-Type':'application/x-www-form-urlencoded',
  'Accept':'application/json',
  'master_key':'API_KEY'

};

$.ajax({
  url: '/https://app.getrakam.com/project/schema',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /project/schema`

*Get collection schema*

> Body parameter

```yaml
project: string

```

<h3 id="schema-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[listQueries](#schemalistqueries)|false|none|
|» project|body|string|false|none|

> Example responses

> 200 Response

```json
[
  {}
]
```

<h3 id="schema-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|successful operation|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Project does not exist.|None|

<h3 id="schema-responseschema">Response Schema</h3>

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
master_key
</aside>

# Schemas

<h2 id="tocSuserhttpservice_search">UserHttpService_search</h2>

<a id="schemauserhttpservice_search"></a>

```json
{
  "project": "string",
  "filter": "string",
  "event_filters": [
    {
      "collection": "string",
      "aggregation": {
        "field": "string",
        "minimum": 0,
        "maximum": 0,
        "type": "COUNT"
      },
      "filterExpression": "string"
    }
  ],
  "sorting": {
    "column": "string",
    "order": "asc"
  },
  "offset": 0,
  "limit": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|project|string|false|none|none|
|filter|string|false|none|none|
|event_filters|[[EventFilter](#schemaeventfilter)]|false|none|none|
|sorting|[Sorting](#schemasorting)|false|none|none|
|offset|integer(int32)|false|none|none|
|limit|integer(int32)|false|none|none|

<h2 id="tocSuser">User</h2>

<a id="schemauser"></a>

```json
{
  "project": "string",
  "id": {},
  "properties": {
    "property1": {},
    "property2": {}
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|project|string|false|none|none|
|id|object|false|none|none|
|properties|object|false|none|none|
|» **additionalProperties**|object|false|none|none|

<h2 id="tocSmessage">Message</h2>

<a id="schemamessage"></a>

```json
{
  "id": 0,
  "content": "string",
  "from_user": {},
  "to_user": {},
  "parentId": 0,
  "seen": false,
  "time": 0,
  "project": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int32)|false|none|none|
|content|string|false|none|none|
|from_user|object|false|none|none|
|to_user|object|false|none|none|
|parentId|integer(int32)|false|none|none|
|seen|boolean|false|none|none|
|time|integer(int64)|false|none|none|
|project|string|false|none|none|

<h2 id="tocSreference">Reference</h2>

<a id="schemareference"></a>

```json
{
  "type": "COLUMN",
  "value": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|type|string|false|none|none|
|value|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|COLUMN|
|type|REFERENCE|

<h2 id="tocSuserhttpservice_create">UserHttpService_create</h2>

<a id="schemauserhttpservice_create"></a>

```json
{
  "project": "string",
  "properties": {
    "property1": {},
    "property2": {}
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|project|string|false|none|none|
|properties|object|false|none|none|
|» **additionalProperties**|object|false|none|none|

<h2 id="tocSeventfilter">EventFilter</h2>

<a id="schemaeventfilter"></a>

```json
{
  "collection": "string",
  "aggregation": {
    "field": "string",
    "minimum": 0,
    "maximum": 0,
    "type": "COUNT"
  },
  "filterExpression": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|collection|string|false|none|none|
|aggregation|[EventFilterAggregation](#schemaeventfilteraggregation)|false|none|none|
|filterExpression|string|false|none|none|

<h2 id="tocSjsonresponse">JsonResponse</h2>

<a id="schemajsonresponse"></a>

```json
{
  "success": false,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|success|boolean|false|none|none|
|message|string|false|none|none|

<h2 id="tocSsorting">Sorting</h2>

<a id="schemasorting"></a>

```json
{
  "column": "string",
  "order": "asc"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|column|string|false|none|none|
|order|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|order|asc|
|order|desc|

<h2 id="tocSschemafield">SchemaField</h2>

<a id="schemaschemafield"></a>

```json
{
  "name": "string",
  "type": "STRING",
  "nullable": false,
  "unique": false,
  "descriptiveName": "string",
  "description": "string",
  "category": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|name|string|false|read-only|none|
|type|string|false|read-only|none|
|nullable|boolean|false|read-only|none|
|unique|boolean|false|read-only|none|
|descriptiveName|string|false|read-only|none|
|description|string|false|read-only|none|
|category|string|false|read-only|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|STRING|
|type|ARRAY|
|type|LONG|
|type|DOUBLE|
|type|BOOLEAN|
|type|DATE|
|type|HYPERLOGLOG|
|type|TIME|
|type|TIMESTAMP|

<h2 id="tocSqueryresult">QueryResult</h2>

<a id="schemaqueryresult"></a>

```json
{
  "metadata": [
    {
      "name": "string",
      "type": "STRING",
      "nullable": false,
      "unique": false,
      "descriptiveName": "string",
      "description": "string",
      "category": "string"
    }
  ],
  "result": [
    [
      {}
    ]
  ],
  "error": {
    "message": "string",
    "sqlState": "string",
    "errorCode": 0
  },
  "properties": {
    "property1": {},
    "property2": {}
  },
  "failed": false
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|metadata|[[SchemaField](#schemaschemafield)]|false|none|none|
|result|[array]|false|none|none|
|error|[QueryError](#schemaqueryerror)|false|none|none|
|properties|object|false|none|none|
|» **additionalProperties**|object|false|none|none|
|failed|boolean|false|none|none|

<h2 id="tocScontinuousquery">ContinuousQuery</h2>

<a id="schemacontinuousquery"></a>

```json
{
  "project": "string",
  "name": "string",
  "query": "string",
  "table_name": "string",
  "collections": [
    "string"
  ],
  "partition_keys": [
    "string"
  ],
  "options": {
    "property1": {},
    "property2": {}
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|project|string|false|none|none|
|name|string|false|none|none|
|query|string|false|none|none|
|table_name|string|false|none|none|
|collections|[string]|false|none|none|
|partition_keys|[string]|false|none|none|
|options|object|false|none|none|
|» **additionalProperties**|object|false|none|none|

<h2 id="tocSeventexplorerhttpservice_execute">EventExplorerHttpService_execute</h2>

<a id="schemaeventexplorerhttpservice_execute"></a>

```json
{
  "project": "string",
  "measure": {
    "column": "string",
    "aggregation": "COUNT"
  },
  "grouping": {
    "type": "COLUMN",
    "value": "string"
  },
  "segment": {
    "type": "COLUMN",
    "value": "string"
  },
  "filterExpression": "string",
  "startDate": "2020-04-03",
  "endDate": "2020-04-03",
  "collections": [
    "string"
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|project|string|false|none|none|
|measure|[Measure](#schemameasure)|false|none|none|
|grouping|[Reference](#schemareference)|false|none|none|
|segment|[Reference](#schemareference)|false|none|none|
|filterExpression|string|false|none|none|
|startDate|string(date)|false|none|none|
|endDate|string(date)|false|none|none|
|collections|[string]|false|none|none|

<h2 id="tocSmeasure">Measure</h2>

<a id="schemameasure"></a>

```json
{
  "column": "string",
  "aggregation": "COUNT"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|column|string|false|none|none|
|aggregation|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|aggregation|COUNT|
|aggregation|COUNT_UNIQUE|
|aggregation|SUM|
|aggregation|MINIMUM|
|aggregation|MAXIMUM|
|aggregation|APPROXIMATE_UNIQUE|
|aggregation|VARIANCE|
|aggregation|POPULATION_VARIANCE|
|aggregation|STANDARD_DEVIATION|
|aggregation|AVERAGE|

<h2 id="tocScreateuserresponse">CreateUserResponse</h2>

<a id="schemacreateuserresponse"></a>

```json
{
  "identifier": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|identifier|object|false|none|none|

<h2 id="tocSmetadataresponse">MetadataResponse</h2>

<a id="schemametadataresponse"></a>

```json
{
  "columns": [
    {
      "name": "string",
      "type": "STRING",
      "nullable": false,
      "unique": false,
      "descriptiveName": "string",
      "description": "string",
      "category": "string"
    }
  ],
  "identifierColumn": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|columns|[[SchemaField](#schemaschemafield)]|false|none|none|
|identifierColumn|string|false|none|none|

<h2 id="tocSorg.rakam.collection.event.eventcollectionhttpservice.collect">org.rakam.collection.event.EventCollectionHttpService.collect</h2>

<a id="schemaorg.rakam.collection.event.eventcollectionhttpservice.collect"></a>

```json
{
  "project": "",
  "collection": "",
  "properties": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|project|string|true|none|none|
|collection|string|true|none|none|
|properties|object|true|none|none|

<h2 id="tocSmaterializedview">MaterializedView</h2>

<a id="schemamaterializedview"></a>

```json
{
  "project": "string",
  "name": "string",
  "table_name": "string",
  "query": "string",
  "update_interval": "string",
  "options": {
    "property1": {},
    "property2": {}
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|project|string|false|none|none|
|name|string|false|none|none|
|table_name|string|false|none|none|
|query|string|false|none|none|
|update_interval|string|false|none|none|
|options|object|false|none|none|
|» **additionalProperties**|object|false|none|none|

<h2 id="tocSqueryerror">QueryError</h2>

<a id="schemaqueryerror"></a>

```json
{
  "message": "string",
  "sqlState": "string",
  "errorCode": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|message|string|false|none|none|
|sqlState|string|false|none|none|
|errorCode|integer(int32)|false|none|none|

<h2 id="tocSeventfilteraggregation">EventFilterAggregation</h2>

<a id="schemaeventfilteraggregation"></a>

```json
{
  "field": "string",
  "minimum": 0,
  "maximum": 0,
  "type": "COUNT"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|field|string|false|none|none|
|minimum|integer(int64)|false|none|none|
|maximum|integer(int64)|false|none|none|
|type|string|false|none|none|

#### Enumerated Values

|Property|Value|
|---|---|
|type|COUNT|
|type|COUNT_UNIQUE|
|type|SUM|
|type|MINIMUM|
|type|MAXIMUM|
|type|APPROXIMATE_UNIQUE|
|type|VARIANCE|
|type|POPULATION_VARIANCE|
|type|STANDARD_DEVIATION|
|type|AVERAGE|

<h2 id="tocSfunnelquery">FunnelQuery</h2>

<a id="schemafunnelquery"></a>

```json
{
  "project": "string",
  "steps": [
    {
      "collection": "string",
      "filterExpression": "string"
    }
  ],
  "dimension": "string",
  "startDate": "2020-04-03",
  "endDate": "2020-04-03",
  "enableOtherGrouping": true
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|project|string|false|none|none|
|steps|[[FunnelStep](#schemafunnelstep)]|false|none|none|
|dimension|string|false|none|none|
|startDate|string(date)|false|none|none|
|endDate|string(date)|false|none|none|
|enableOtherGrouping|boolean|false|none|none|

<h2 id="tocSfunnelstep">FunnelStep</h2>

<a id="schemafunnelstep"></a>

```json
{
  "collection": "string",
  "filterExpression": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|collection|string|false|none|none|
|filterExpression|string|false|none|none|

