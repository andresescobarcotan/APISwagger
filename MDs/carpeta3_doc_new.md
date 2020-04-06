---
title: 'Swagger Petstore Now with cats, dogs and parrots!'
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

<h1 id="swagger-petstore-now-with-cats-dogs-and-parrots-">Swagger Petstore Now with cats, dogs and parrots! v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

Base URLs:

* <a href="http://petstore.swagger.io/v1">http://petstore.swagger.io/v1</a>

 License: MIT

<h1 id="swagger-petstore-now-with-cats-dogs-and-parrots--pets">pets</h1>

## listPets

<a id="opIdlistPets"></a>

> Code samples

```java
URL obj = new URL("http://petstore.swagger.io/v1/pets");
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
    req, err := http.NewRequest("GET", "http://petstore.swagger.io/v1/pets", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://petstore.swagger.io/v1/pets',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /pets`

*List all pets*

<h3 id="listpets-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|limit|query|integer(int32)|false|How many items to return at one time (max 100)|

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "name": "string",
    "tag": "string"
  }
]
```

<h3 id="listpets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|A paged array of pets|[Pets](#schemapets)|
|default|Default|unexpected error|[Error](#schemaerror)|

### Response Headers

|Status|Header|Type|Format|Description|
|---|---|---|---|---|
|200|x-next|string||A link to the next page of responses|

<aside class="success">
This operation does not require authentication
</aside>

## createPets

<a id="opIdcreatePets"></a>

> Code samples

```java
URL obj = new URL("http://petstore.swagger.io/v1/pets");
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
        "Accept": []string{"application/json"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "http://petstore.swagger.io/v1/pets", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://petstore.swagger.io/v1/pets',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`POST /pets`

*Create a pet*

> Example responses

> default Response

```json
{
  "code": 0,
  "message": "string"
}
```

<h3 id="createpets-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|201|[Created](https://tools.ietf.org/html/rfc7231#section-6.3.2)|Null response|None|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

## showPetById

<a id="opIdshowPetById"></a>

> Code samples

```java
URL obj = new URL("http://petstore.swagger.io/v1/pets/{petId}");
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
    req, err := http.NewRequest("GET", "http://petstore.swagger.io/v1/pets/{petId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: 'http://petstore.swagger.io/v1/pets/{petId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

`GET /pets/{petId}`

*Info for a specific pet*

<h3 id="showpetbyid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|petId|path|string|true|The id of the pet to retrieve|

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "name": "string",
    "tag": "string"
  }
]
```

<h3 id="showpetbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Expected response to a valid request|[Pets](#schemapets)|
|default|Default|unexpected error|[Error](#schemaerror)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSpet">Pet</h2>

<a id="schemapet"></a>

```json
{
  "id": 0,
  "name": "string",
  "tag": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|integer(int64)|true|none|none|
|name|string|true|none|none|
|tag|string|false|none|none|

<h2 id="tocSpets">Pets</h2>

<a id="schemapets"></a>

```json
[
  {
    "id": 0,
    "name": "string",
    "tag": "string"
  }
]

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Pet](#schemapet)]|false|none|none|

<h2 id="tocSerror">Error</h2>

<a id="schemaerror"></a>

```json
{
  "code": 0,
  "message": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|code|integer(int32)|true|none|none|
|message|string|true|none|none|

