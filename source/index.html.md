---
title: Subscription Suite API
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - javascript--nodejs: Node.JS
  - ruby: Ruby
  - python: Python
  - java: Java
  - go: Go
toc_footers:
  - '<a href="http://swagger.io">Find out more about Swagger</a>'
includes: []
search: true
highlight_theme: darkula
headingLevel: 2

---

<h1 id="Subscription-Suite-API">Subscription Suite API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

This is the API that is used by the Subscription Suite Angular 6 frontend components. You can find out more about Subscription Suite at [https://www.subscription-suite.com](https://www.subscription-suite.com).

Email: <a href="mailto:hello@keylight.de">Support</a> 

# Authentication

- HTTP Authentication, scheme: bearer 

* API Key (cookieAuth)
    - Parameter Name: **user**, in: cookie. 

<h1 id="Subscription-Suite-API-account">account</h1>

Manage data related to Zuora billing accounts

## getAccount

<a id="opIdgetAccount"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /account \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /account HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/account',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/account',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/account',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/account', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/account");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/account", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /account`

*Get summarized information about an account, in particular name and the address information*

> Example responses

> 200 Response

```json
{
  "billToContact": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "country": "string",
    "county": "string",
    "fax": "string",
    "firstName": "string",
    "lastName": "string",
    "state": "string",
    "taxRegion": "string",
    "workEmail": "string",
    "workPhone": "string",
    "zipCode": "string"
  },
  "currency": "string",
  "name": "string",
  "paymentMethod": {
    "id": "string",
    "type": "string",
    "creditCardNumber": "string",
    "creditCardHolder": "string",
    "creditCardExpirationMonth": 0,
    "creditCardExpirationYear": 0,
    "iban": "string",
    "bankAccountHolder": "string"
  },
  "soldToContact": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "country": "string",
    "county": "string",
    "fax": "string",
    "firstName": "string",
    "lastName": "string",
    "state": "string",
    "taxRegion": "string",
    "workEmail": "string",
    "workPhone": "string",
    "zipCode": "string"
  },
  "vatId": "string"
}
```

<h3 id="getaccount-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="getaccount-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» billToContact|object|false|none|none|
|»» address1|string|false|none|none|
|»» address2|string|false|none|none|
|»» city|string|false|none|none|
|»» country|string|false|none|none|
|»» county|string|false|none|none|
|»» fax|string|false|none|none|
|»» firstName|string|false|none|none|
|»» lastName|string|false|none|none|
|»» state|string|false|none|none|
|»» taxRegion|string|false|none|none|
|»» workEmail|string|false|none|none|
|»» workPhone|string|false|none|none|
|»» zipCode|string|false|none|none|
|» currency|string|false|none|none|
|» name|string|false|none|none|
|» paymentMethod|object|false|none|none|
|»» id|string|false|none|none|
|»» type|string|false|none|none|
|»» creditCardNumber|string|false|none|none|
|»» creditCardHolder|string|false|none|none|
|»» creditCardExpirationMonth|number|false|none|none|
|»» creditCardExpirationYear|number|false|none|none|
|»» iban|string|false|none|none|
|»» bankAccountHolder|string|false|none|none|
|» soldToContact|object|false|none|none|
|» vatId|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## updateAccount

<a id="opIdupdateAccount"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /account \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /account HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/account',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "billToContact": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "country": "string",
    "county": "string",
    "fax": "string",
    "firstName": "string",
    "lastName": "string",
    "state": "string",
    "taxRegion": "string",
    "workEmail": "string",
    "workPhone": "string",
    "zipCode": "string"
  },
  "name": "string",
  "soldToContact": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "country": "string",
    "county": "string",
    "fax": "string",
    "firstName": "string",
    "lastName": "string",
    "state": "string",
    "taxRegion": "string",
    "workEmail": "string",
    "workPhone": "string",
    "zipCode": "string"
  },
  "vatId": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/account',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/account',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/account', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/account");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/account", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /account`

*Update an existing account*

> Body parameter

```json
{
  "billToContact": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "country": "string",
    "county": "string",
    "fax": "string",
    "firstName": "string",
    "lastName": "string",
    "state": "string",
    "taxRegion": "string",
    "workEmail": "string",
    "workPhone": "string",
    "zipCode": "string"
  },
  "name": "string",
  "soldToContact": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "country": "string",
    "county": "string",
    "fax": "string",
    "firstName": "string",
    "lastName": "string",
    "state": "string",
    "taxRegion": "string",
    "workEmail": "string",
    "workPhone": "string",
    "zipCode": "string"
  },
  "vatId": "string"
}
```

<h3 id="updateaccount-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|true|none|
|» billToContact|body|object|false|none|
|»» address1|body|string|false|none|
|»» address2|body|string|false|none|
|»» city|body|string|false|none|
|»» country|body|string|false|none|
|»» county|body|string|false|none|
|»» fax|body|string|false|none|
|»» firstName|body|string|false|none|
|»» lastName|body|string|false|none|
|»» state|body|string|false|none|
|»» taxRegion|body|string|false|none|
|»» workEmail|body|string|false|none|
|»» workPhone|body|string|false|none|
|»» zipCode|body|string|false|none|
|» name|body|string|false|none|
|» soldToContact|body|object|false|none|
|» vatId|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="updateaccount-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="updateaccount-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## getInvoices

<a id="opIdgetInvoices"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /account/invoice \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /account/invoice HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/account/invoice',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/account/invoice',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/account/invoice',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/account/invoice', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/account/invoice");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/account/invoice", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /account/invoice`

*Get posted invoices for a user*

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "amount": 0,
    "amountWithoutTax": 0,
    "balance": 0,
    "dueDate": "2018-10-02",
    "invoiceDate": "2018-10-02",
    "invoiceNumber": "string",
    "taxAmount": 0
  }
]
```

<h3 id="getinvoices-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="getinvoices-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|string|false|none|none|
|» amount|number|false|none|none|
|» amountWithoutTax|number|false|none|none|
|» balance|number|false|none|none|
|» dueDate|string(date)|false|none|none|
|» invoiceDate|string(date)|false|none|none|
|» invoiceNumber|string|false|none|none|
|» taxAmount|number|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## getSubscriptions

<a id="opIdgetSubscriptions"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /account/subscription \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /account/subscription HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/account/subscription',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/account/subscription',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/account/subscription',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/account/subscription', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/account/subscription");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/account/subscription", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /account/subscription`

*Get subscriptions for a user*

> Example responses

> 200 Response

```json
{
  "oneTimeOrders": [
    {
      "autoRenew": true,
      "currentTerm": 0,
      "contractEffectiveDate": "2018-10-02",
      "customerAcceptanceDate": "2018-10-02",
      "id": "string",
      "initialTerm": 0,
      "invoiceOwnerAccountId": "string",
      "invoiceOwnerAccountName": "string",
      "invoiceOwnerAccountNumber": "string",
      "latestRateplans": [
        {
          "id": "string",
          "type": "string"
        }
      ],
      "ratePlans": [
        {
          "id": "string",
          "type": "string"
        }
      ],
      "renewalSetting": "string",
      "renewalTerm": 0,
      "serviceActivationDate": "2018-10-02",
      "status": "string",
      "subscriptionNumber": "string",
      "subscriptionStartDate": "2018-10-02",
      "termEndDate": "2018-10-02",
      "termStartDate": "2018-10-02",
      "termType": "string"
    }
  ]
}
```

<h3 id="getsubscriptions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="getsubscriptions-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» oneTimeOrders|[object]|false|none|none|
|»» autoRenew|boolean|false|none|none|
|»» currentTerm|number|false|none|none|
|»» contractEffectiveDate|string(date)|false|none|none|
|»» customerAcceptanceDate|string(date)|false|none|none|
|»» id|string|false|none|none|
|»» initialTerm|number|false|none|none|
|»» invoiceOwnerAccountId|string|false|none|none|
|»» invoiceOwnerAccountName|string|false|none|none|
|»» invoiceOwnerAccountNumber|string|false|none|none|
|»» latestRateplans|[[RatePlan](#schemarateplan)]|false|none|none|
|»»» id|string|false|none|none|
|»»» type|string|false|none|none|
|»» ratePlans|[[RatePlan](#schemarateplan)]|false|none|none|
|»» renewalSetting|string|false|none|none|
|»» renewalTerm|number|false|none|none|
|»» serviceActivationDate|string(date)|false|none|none|
|»» status|string|false|none|none|
|»» subscriptionNumber|string|false|none|none|
|»» subscriptionStartDate|string(date)|false|none|none|
|»» termEndDate|string(date)|false|none|none|
|»» termStartDate|string(date)|false|none|none|
|»» termType|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## validateVatId

<a id="opIdvalidateVatId"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /account/vat-validate/{vatId} \
  -H 'Accept: application/json'

```

```http
GET /account/vat-validate/{vatId} HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/account/vat-validate/{vatId}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/account/vat-validate/{vatId}',
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

result = RestClient.get '/account/vat-validate/{vatId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/account/vat-validate/{vatId}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/account/vat-validate/{vatId}");
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
    req, err := http.NewRequest("GET", "/account/vat-validate/{vatId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /account/vat-validate/{vatId}`

*Validate a VAT ID*

<h3 id="validatevatid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|vatId|path|string|true|VAT ID that needs to be checked|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="validatevatid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="validatevatid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Subscription-Suite-API-auth">auth</h1>

User credentials, registration, login, SSO

## login

<a id="opIdlogin"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /login \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /login HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/login',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "user": {
    "email": "string",
    "password": "string"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/login',
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

result = RestClient.post '/login',
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

r = requests.post('/login', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/login");
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
    req, err := http.NewRequest("POST", "/login", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /login`

*Log a user in, create a JWT and set cookie*

> Body parameter

```json
{
  "user": {
    "email": "string",
    "password": "string"
  }
}
```

<h3 id="login-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» user|body|object|false|none|
|»» email|body|string|false|none|
|»» password|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "token": "string"
}
```

<h3 id="login-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|

<h3 id="login-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» token|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## loginAsGuest

<a id="opIdloginAsGuest"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /login/guest \
  -H 'Accept: application/json'

```

```http
POST /login/guest HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/login/guest',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/login/guest',
{
  method: 'POST',

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

result = RestClient.post '/login/guest',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/login/guest', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/login/guest");
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
    req, err := http.NewRequest("POST", "/login/guest", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /login/guest`

*Create a JWT to authenticate a guest user and set cookie*

> Example responses

> 200 Response

```json
{
  "token": "string"
}
```

<h3 id="loginasguest-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="loginasguest-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» token|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## logout

<a id="opIdlogout"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /logout \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /logout HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/logout',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/logout',
{
  method: 'POST',

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/logout',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/logout', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/logout");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/logout", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /logout`

*Log the user out*

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="logout-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="logout-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## initPasswordReset

<a id="opIdinitPasswordReset"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /password-reset/init \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /password-reset/init HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/password-reset/init',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "email": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/password-reset/init',
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

result = RestClient.post '/password-reset/init',
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

r = requests.post('/password-reset/init', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/password-reset/init");
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
    req, err := http.NewRequest("POST", "/password-reset/init", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /password-reset/init`

*Initiate a password reset. An email to confirm will be sent to the user*

> Body parameter

```json
{
  "email": "string"
}
```

<h3 id="initpasswordreset-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» email|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="initpasswordreset-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<h3 id="initpasswordreset-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## confirmPasswordReset

<a id="opIdconfirmPasswordReset"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /password-reset/confirm \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /password-reset/confirm HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/password-reset/confirm',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "confirmKey": "string",
  "password": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/password-reset/confirm',
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

result = RestClient.post '/password-reset/confirm',
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

r = requests.post('/password-reset/confirm', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/password-reset/confirm");
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
    req, err := http.NewRequest("POST", "/password-reset/confirm", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /password-reset/confirm`

*Confirm a password reset with confirm key and new password*

> Body parameter

```json
{
  "confirmKey": "string",
  "password": "string"
}
```

<h3 id="confirmpasswordreset-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» confirmKey|body|string|false|none|
|» password|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="confirmpasswordreset-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<h3 id="confirmpasswordreset-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## post__register

> Code samples

```shell
# You can also use wget
curl -X POST /register \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /register HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/register',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "user": {
    "email": "string",
    "password": "string"
  }
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/register',
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

result = RestClient.post '/register',
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

r = requests.post('/register', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/register");
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
    req, err := http.NewRequest("POST", "/register", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /register`

> Body parameter

```json
{
  "user": {
    "email": "string",
    "password": "string"
  }
}
```

<h3 id="post__register-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» user|body|object|false|none|
|»» email|body|string|false|none|
|»» password|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "token": "string"
}
```

<h3 id="post__register-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|

<h3 id="post__register-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» token|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Subscription-Suite-API-payment-method">payment-method</h1>

Creating and updating payment methods. Helpers to deal with Paypal and Zuora integration.

## getPaymentMethodForUser

<a id="opIdgetPaymentMethodForUser"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /payment-method \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /payment-method HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/payment-method',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/payment-method',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/payment-method',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/payment-method', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/payment-method");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/payment-method", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /payment-method`

*Get the default payment method of a user*

> Example responses

> 200 Response

```json
{
  "id": "string",
  "type": "string",
  "creditCardNumber": "string",
  "creditCardHolder": "string",
  "creditCardExpirationMonth": 0,
  "creditCardExpirationYear": 0,
  "iban": "string",
  "bankAccountHolder": "string"
}
```

<h3 id="getpaymentmethodforuser-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[PaymentMethod](#schemapaymentmethod)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## updatePaymentMethod

<a id="opIdupdatePaymentMethod"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /payment-method \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /payment-method HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/payment-method',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "id": 0,
  "token": "string",
  "creditCardNumber": "string",
  "creditCardHolder": "string",
  "creditCardExpirationMonth": 0,
  "creditCardExpirationYear": 0,
  "iban": "string",
  "bankAccountHolder": "string"
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/payment-method',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/payment-method',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/payment-method', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/payment-method");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/payment-method", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /payment-method`

*Update user's payment method*

> Body parameter

```json
{
  "id": 0,
  "token": "string",
  "creditCardNumber": "string",
  "creditCardHolder": "string",
  "creditCardExpirationMonth": 0,
  "creditCardExpirationYear": 0,
  "iban": "string",
  "bankAccountHolder": "string"
}
```

<h3 id="updatepaymentmethod-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|object|false|none|
|» id|body|integer|false|none|
|» token|body|string|false|none|
|» creditCardNumber|body|string|false|none|
|» creditCardHolder|body|string|false|none|
|» creditCardExpirationMonth|body|number|false|none|
|» creditCardExpirationYear|body|number|false|none|
|» iban|body|string|false|none|
|» bankAccountHolder|body|string|false|none|

> Example responses

> 200 Response

```json
{
  "id": "string"
}
```

<h3 id="updatepaymentmethod-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="updatepaymentmethod-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## getPaymentMethodById

<a id="opIdgetPaymentMethodById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /payment-method/{id} \
  -H 'Accept: application/json'

```

```http
GET /payment-method/{id} HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/payment-method/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/payment-method/{id}',
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

result = RestClient.get '/payment-method/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/payment-method/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/payment-method/{id}");
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
    req, err := http.NewRequest("GET", "/payment-method/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /payment-method/{id}`

*Get a payment method by Zuora Id*

<h3 id="getpaymentmethodbyid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The Zuora ID of a payment method|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "type": "string",
  "creditCardNumber": "string",
  "creditCardHolder": "string",
  "creditCardExpirationMonth": 0,
  "creditCardExpirationYear": 0,
  "iban": "string",
  "bankAccountHolder": "string"
}
```

<h3 id="getpaymentmethodbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[PaymentMethod](#schemapaymentmethod)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## initPaypal

<a id="opIdinitPaypal"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /payment-method/{id}/paypal/init \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
GET /payment-method/{id}/paypal/init HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/payment-method/{id}/paypal/init',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/payment-method/{id}/paypal/init',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/payment-method/{id}/paypal/init',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/payment-method/{id}/paypal/init', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/payment-method/{id}/paypal/init");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/payment-method/{id}/paypal/init", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /payment-method/{id}/paypal/init`

*Get a Paypal token for a Paypal payment method*

<h3 id="initpaypal-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Subscription Suite payment method|

> Example responses

> 200 Response

```json
{
  "token": "string"
}
```

<h3 id="initpaypal-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="initpaypal-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» token|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## getZuoraPaymentPageSignature

<a id="opIdgetZuoraPaymentPageSignature"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /payment-method/{id}/signature \
  -H 'Accept: application/json'

```

```http
GET /payment-method/{id}/signature HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/payment-method/{id}/signature',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/payment-method/{id}/signature',
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

result = RestClient.get '/payment-method/{id}/signature',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/payment-method/{id}/signature', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/payment-method/{id}/signature");
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
    req, err := http.NewRequest("GET", "/payment-method/{id}/signature", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /payment-method/{id}/signature`

*Get the signature to render a Zuora payment page in an iFrame*

<h3 id="getzuorapaymentpagesignature-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Subscription Suite payment method|
|locale|query|string|false|Locale to render the Zuora payment page in certain language|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "key": "string",
  "locale": "string",
  "signature": "string",
  "token": "string"
}
```

<h3 id="getzuorapaymentpagesignature-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<h3 id="getzuorapaymentpagesignature-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|string|false|none|none|
|» key|string|false|none|none|
|» locale|string|false|none|none|
|» signature|string|false|none|none|
|» token|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## getAvailablePaymentMethods

<a id="opIdgetAvailablePaymentMethods"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /payment-method/available \
  -H 'Accept: application/json'

```

```http
GET /payment-method/available HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/payment-method/available',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/payment-method/available',
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

result = RestClient.get '/payment-method/available',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/payment-method/available', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/payment-method/available");
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
    req, err := http.NewRequest("GET", "/payment-method/available", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /payment-method/available`

*Get the available payment methods for a certain user type*

<h3 id="getavailablepaymentmethods-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|country|query|string|false|Country code to display available payment methods for|

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "type": "string"
  }
]
```

<h3 id="getavailablepaymentmethods-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getavailablepaymentmethods-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|integer|false|none|none|
|» type|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Subscription-Suite-API-quote">quote</h1>

Quote acceptance processes with Salesforce integration

## getQuote

<a id="opIdgetQuote"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /quote/{id} \
  -H 'Accept: application/json'

```

```http
GET /quote/{id} HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/quote/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/quote/{id}',
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

result = RestClient.get '/quote/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/quote/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/quote/{id}");
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
    req, err := http.NewRequest("GET", "/quote/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /quote/{id}`

*Get quote data from Salesforce*

<h3 id="getquote-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The ID of a Salesforce quote|

> Example responses

> 200 Response

```json
{
  "billToContact": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "country": "string",
    "county": "string",
    "fax": "string",
    "firstName": "string",
    "lastName": "string",
    "state": "string",
    "taxRegion": "string",
    "workEmail": "string",
    "workPhone": "string",
    "zipCode": "string"
  },
  "currency": "string",
  "name": "string",
  "quoteNumber": "string",
  "ratePlans": [
    {
      "id": "string",
      "type": "string"
    }
  ],
  "soldToContact": {
    "address1": "string",
    "address2": "string",
    "city": "string",
    "country": "string",
    "county": "string",
    "fax": "string",
    "firstName": "string",
    "lastName": "string",
    "state": "string",
    "taxRegion": "string",
    "workEmail": "string",
    "workPhone": "string",
    "zipCode": "string"
  },
  "startDate": "2018-10-02",
  "term": "string",
  "validUntiDate": "2018-10-02",
  "vatId": "string"
}
```

<h3 id="getquote-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<h3 id="getquote-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» billToContact|object|false|none|none|
|»» address1|string|false|none|none|
|»» address2|string|false|none|none|
|»» city|string|false|none|none|
|»» country|string|false|none|none|
|»» county|string|false|none|none|
|»» fax|string|false|none|none|
|»» firstName|string|false|none|none|
|»» lastName|string|false|none|none|
|»» state|string|false|none|none|
|»» taxRegion|string|false|none|none|
|»» workEmail|string|false|none|none|
|»» workPhone|string|false|none|none|
|»» zipCode|string|false|none|none|
|» currency|string|false|none|none|
|» name|string|false|none|none|
|» quoteNumber|string|false|none|none|
|» ratePlans|[[RatePlan](#schemarateplan)]|false|none|none|
|»» id|string|false|none|none|
|»» type|string|false|none|none|
|» soldToContact|object|false|none|none|
|» startDate|string(date)|false|none|none|
|» term|string|false|none|none|
|» validUntiDate|string(date)|false|none|none|
|» vatId|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## confirmQuote

<a id="opIdconfirmQuote"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /quote/{id} \
  -H 'Accept: application/json'

```

```http
POST /quote/{id} HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/quote/{id}',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/quote/{id}',
{
  method: 'POST',

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

result = RestClient.post '/quote/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.post('/quote/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/quote/{id}");
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
    req, err := http.NewRequest("POST", "/quote/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /quote/{id}`

*Confirm a quote in Salesforce and send it to Zuora*

<h3 id="confirmquote-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The ID of a Salesforce quote|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="confirmquote-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<h3 id="confirmquote-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Subscription-Suite-API-product-catalog">product-catalog</h1>

Fetching and managing the Zuora product catalog

## getRatePlans

<a id="opIdgetRatePlans"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /rateplan \
  -H 'Accept: application/json'

```

```http
GET /rateplan HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/rateplan',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/rateplan',
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

result = RestClient.get '/rateplan',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/rateplan', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/rateplan");
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
    req, err := http.NewRequest("GET", "/rateplan", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /rateplan`

*Get all Zuora product rate plans*

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "type": "string"
  }
]
```

<h3 id="getrateplans-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getrateplans-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[RatePlan](#schemarateplan)]|false|none|none|
|» id|string|false|none|none|
|» type|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## getRatePlanById

<a id="opIdgetRatePlanById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /rateplan/{id} \
  -H 'Accept: application/json'

```

```http
GET /rateplan/{id} HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/rateplan/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/rateplan/{id}',
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

result = RestClient.get '/rateplan/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/rateplan/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/rateplan/{id}");
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
    req, err := http.NewRequest("GET", "/rateplan/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /rateplan/{id}`

*Get a Zuora product rate plan*

<h3 id="getrateplanbyid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Subscription Suite rate plan|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "type": "string"
}
```

<h3 id="getrateplanbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[RatePlan](#schemarateplan)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## getProducts

<a id="opIdgetProducts"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /product \
  -H 'Accept: application/json'

```

```http
GET /product HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/product',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/product',
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

result = RestClient.get '/product',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/product', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/product");
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
    req, err := http.NewRequest("GET", "/product", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /product`

*Get all Zuora products*

> Example responses

> 200 Response

```json
[
  {
    "id": "string",
    "type": "string"
  }
]
```

<h3 id="getproducts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getproducts-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Product](#schemaproduct)]|false|none|none|
|» id|string|false|none|none|
|» type|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## getProductById

<a id="opIdgetProductById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /product/{id} \
  -H 'Accept: application/json'

```

```http
GET /product/{id} HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/product/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/product/{id}',
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

result = RestClient.get '/product/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/product/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/product/{id}");
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
    req, err := http.NewRequest("GET", "/product/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /product/{id}`

*Get a Zuora product*

<h3 id="getproductbyid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Subscription Suite product|

> Example responses

> 200 Response

```json
{
  "id": "string",
  "type": "string"
}
```

<h3 id="getproductbyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Product](#schemaproduct)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Subscription-Suite-API-shop">shop</h1>

Query shop pages with multiple product selection steps

## getShopPageById

<a id="opIdgetShopPageById"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /page/{id} \
  -H 'Accept: application/json'

```

```http
GET /page/{id} HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/page/{id}',
  method: 'get',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/page/{id}',
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

result = RestClient.get '/page/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/page/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/page/{id}");
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
    req, err := http.NewRequest("GET", "/page/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /page/{id}`

*Fetches all relevant information to display a shop page*

<h3 id="getshoppagebyid-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The ID of a Subscription Suite shop page|

> Example responses

> 200 Response

```json
{
  "allowVoucher": true,
  "description": "string",
  "id": 0,
  "isActive": true,
  "isCart": true,
  "name": "string",
  "pageId": 0,
  "showCart": true,
  "steps": [
    {
      "description": "string",
      "hasUniqueSelection": true,
      "id": 0,
      "isOptional": true,
      "name": "string",
      "number": 0,
      "ratePlans": [
        {
          "description": "string",
          "effectiveEndDate": "string",
          "effectiveStartDate": "string",
          "featureList": "string",
          "highlight": "string",
          "id": 0,
          "name": "string",
          "product": {
            "description": "string",
            "effectiveEndDate": "string",
            "effectiveStartDate": "string",
            "name": "string",
            "sku": "string"
          },
          "productRatePlanCharges": [
            {
              "billingPeriod": "string",
              "billingTiming": "string",
              "chargeModel": "string",
              "chargeType": "string",
              "defaultQuantity": 0,
              "description": "string",
              "id": 0,
              "name": "string",
              "productRatePlanChargeTiers": [
                {
                  "currency": "string",
                  "endingUnit": "string",
                  "isOveragePrice": true,
                  "price": 0,
                  "priceFormat": "string",
                  "startingUnit": "string"
                }
              ],
              "taxMode": "string",
              "isTaxable": true,
              "uom": "string"
            }
          ]
        }
      ],
      "showCharges": true,
      "showDescription": true,
      "showFeatureList": true,
      "showPeriods": true,
      "showProductName": true,
      "showRatePlanName": true
    }
  ]
}
```

<h3 id="getshoppagebyid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<h3 id="getshoppagebyid-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» allowVoucher|boolean|false|none|none|
|» description|string|false|none|none|
|» id|integer|false|none|none|
|» isActive|boolean|false|none|none|
|» isCart|boolean|false|none|none|
|» name|string|false|none|none|
|» pageId|integer|false|none|none|
|» showCart|boolean|false|none|none|
|» steps|[object]|false|none|none|
|»» description|string|false|none|none|
|»» hasUniqueSelection|boolean|false|none|none|
|»» id|integer|false|none|none|
|»» isOptional|boolean|false|none|none|
|»» name|string|false|none|none|
|»» number|integer|false|none|none|
|»» ratePlans|[object]|false|none|none|
|»»» description|string|false|none|none|
|»»» effectiveEndDate|string|false|none|none|
|»»» effectiveStartDate|string|false|none|none|
|»»» featureList|string|false|none|none|
|»»» highlight|string|false|none|none|
|»»» id|integer|false|none|none|
|»»» name|string|false|none|none|
|»»» product|object|false|none|none|
|»»»» description|string|false|none|none|
|»»»» effectiveEndDate|string|false|none|none|
|»»»» effectiveStartDate|string|false|none|none|
|»»»» name|string|false|none|none|
|»»»» sku|string|false|none|none|
|»»» productRatePlanCharges|[object]|false|none|none|
|»»»» billingPeriod|string|false|none|none|
|»»»» billingTiming|string|false|none|none|
|»»»» chargeModel|string|false|none|none|
|»»»» chargeType|string|false|none|none|
|»»»» defaultQuantity|number|false|none|none|
|»»»» description|string|false|none|none|
|»»»» id|number|false|none|none|
|»»»» name|string|false|none|none|
|»»»» productRatePlanChargeTiers|[object]|false|none|none|
|»»»»» currency|string|false|none|none|
|»»»»» endingUnit|string|false|none|none|
|»»»»» isOveragePrice|boolean|false|none|none|
|»»»»» price|number|false|none|none|
|»»»»» priceFormat|string|false|none|none|
|»»»»» startingUnit|string|false|none|none|
|»»»» taxMode|string|false|none|none|
|»»»» isTaxable|boolean|false|none|none|
|»»»» uom|string|false|none|none|
|»»» showCharges|boolean|false|none|none|
|»»» showDescription|boolean|false|none|none|
|»»» showFeatureList|boolean|false|none|none|
|»»» showPeriods|boolean|false|none|none|
|»»» showProductName|boolean|false|none|none|
|»»» showRatePlanName|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Subscription-Suite-API-subscription">subscription</h1>

Preview, create, and modify subscriptions

## createSubscriptions

<a id="opIdcreateSubscriptions"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /subscription \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
POST /subscription HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/subscription',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '[
  {
    "ratePlan": {
      "id": 0,
      "quantity": 0
    },
    "charges": [
      {
        "id": 0,
        "quantity": 0
      }
    ]
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/subscription',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.post '/subscription',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.post('/subscription', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/subscription");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("POST", "/subscription", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /subscription`

*Create new subscriptions for a user*

> Body parameter

```json
[
  {
    "ratePlan": {
      "id": 0,
      "quantity": 0
    },
    "charges": [
      {
        "id": 0,
        "quantity": 0
      }
    ]
  }
]
```

<h3 id="createsubscriptions-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|array[object]|false|none|

> Example responses

> 200 Response

```json
{
  "success": true,
  "ids": [
    "string"
  ]
}
```

<h3 id="createsubscriptions-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="createsubscriptions-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|
|» ids|[string]|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## previewSubscription

<a id="opIdpreviewSubscription"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /subscription/preview \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /subscription/preview HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/subscription/preview',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '[
  {
    "ratePlan": {
      "id": 0,
      "quantity": 0
    },
    "charges": [
      {
        "id": 0,
        "quantity": 0
      }
    ]
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/subscription/preview',
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

result = RestClient.post '/subscription/preview',
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

r = requests.post('/subscription/preview', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/subscription/preview");
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
    req, err := http.NewRequest("POST", "/subscription/preview", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /subscription/preview`

*Calculate prices for selected rate plans, quantities, and discounts*

> Body parameter

```json
[
  {
    "ratePlan": {
      "id": 0,
      "quantity": 0
    },
    "charges": [
      {
        "id": 0,
        "quantity": 0
      }
    ]
  }
]
```

<h3 id="previewsubscription-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|array[object]|false|none|

> Example responses

> 200 Response

```json
[
  {
    "ratePlan": {
      "id": 0,
      "quantity": 0,
      "price": 0,
      "tax": 0,
      "total": 0
    },
    "charges": [
      {
        "id": 0,
        "quantity": 0,
        "price": 0,
        "tax": 0,
        "total": 0
      }
    ]
  }
]
```

<h3 id="previewsubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|

<h3 id="previewsubscription-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SubscribeOptionWithPrice](#schemasubscribeoptionwithprice)]|false|none|none|
|» ratePlan|object|false|none|none|
|»» id|integer|false|none|none|
|»» quantity|integer|false|none|none|
|»» price|number|false|none|none|
|»» tax|number|false|none|none|
|»» total|number|false|none|none|
|» charges|[object]|false|none|none|
|»» id|integer|false|none|none|
|»» quantity|integer|false|none|none|
|»» price|number|false|none|none|
|»» tax|number|false|none|none|
|»» total|number|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## createAmendment

<a id="opIdcreateAmendment"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /subscription/{id} \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /subscription/{id} HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/subscription/{id}',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '[
  {
    "ratePlan": {
      "id": 0,
      "quantity": 0
    },
    "charges": [
      {
        "id": 0,
        "quantity": 0
      }
    ]
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/subscription/{id}',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/subscription/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/subscription/{id}', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/subscription/{id}");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/subscription/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /subscription/{id}`

*Create amendment for a subscription*

> Body parameter

```json
[
  {
    "ratePlan": {
      "id": 0,
      "quantity": 0
    },
    "charges": [
      {
        "id": 0,
        "quantity": 0
      }
    ]
  }
]
```

<h3 id="createamendment-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The ID of a Zuora subscription|
|body|body|array[object]|false|none|

> Example responses

> 200 Response

```json
{
  "success": true,
  "id": "string"
}
```

<h3 id="createamendment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="createamendment-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|
|» id|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## previewAmendment

<a id="opIdpreviewAmendment"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /subscription/{id}/preview \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /subscription/{id}/preview HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/subscription/{id}/preview',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '[
  {
    "ratePlan": {
      "id": 0,
      "quantity": 0
    },
    "charges": [
      {
        "id": 0,
        "quantity": 0
      }
    ]
  }
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/subscription/{id}/preview',
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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/subscription/{id}/preview',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/subscription/{id}/preview', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/subscription/{id}/preview");
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
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/subscription/{id}/preview", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /subscription/{id}/preview`

*Preview amendment for a subscription*

> Body parameter

```json
[
  {
    "ratePlan": {
      "id": 0,
      "quantity": 0
    },
    "charges": [
      {
        "id": 0,
        "quantity": 0
      }
    ]
  }
]
```

<h3 id="previewamendment-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The ID of a Zuora subscription|
|body|body|array[object]|false|none|

> Example responses

> 200 Response

```json
{
  "current": [
    {
      "ratePlan": {
        "id": 0,
        "quantity": 0,
        "price": 0,
        "tax": 0,
        "total": 0
      },
      "charges": [
        {
          "id": 0,
          "quantity": 0,
          "price": 0,
          "tax": 0,
          "total": 0
        }
      ]
    }
  ],
  "target": [
    {
      "ratePlan": {
        "id": 0,
        "quantity": 0,
        "price": 0,
        "tax": 0,
        "total": 0
      },
      "charges": [
        {
          "id": 0,
          "quantity": 0,
          "price": 0,
          "tax": 0,
          "total": 0
        }
      ]
    }
  ]
}
```

<h3 id="previewamendment-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="previewamendment-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» current|[[SubscribeOptionWithPrice](#schemasubscribeoptionwithprice)]|false|none|none|
|»» ratePlan|object|false|none|none|
|»»» id|integer|false|none|none|
|»»» quantity|integer|false|none|none|
|»»» price|number|false|none|none|
|»»» tax|number|false|none|none|
|»»» total|number|false|none|none|
|»» charges|[object]|false|none|none|
|»»» id|integer|false|none|none|
|»»» quantity|integer|false|none|none|
|»»» price|number|false|none|none|
|»»» tax|number|false|none|none|
|»»» total|number|false|none|none|
|»» target|[[SubscribeOptionWithPrice](#schemasubscribeoptionwithprice)]|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## cancelSubscription

<a id="opIdcancelSubscription"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /subscription/{id}/cancel \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /subscription/{id}/cancel HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/subscription/{id}/cancel',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/subscription/{id}/cancel',
{
  method: 'PUT',

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/subscription/{id}/cancel',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/subscription/{id}/cancel', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/subscription/{id}/cancel");
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
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/subscription/{id}/cancel", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /subscription/{id}/cancel`

*Cancel a subscription*

<h3 id="cancelsubscription-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The ID of a Zuora subscription|

> Example responses

> 200 Response

```json
{
  "success": true,
  "id": "string"
}
```

<h3 id="cancelsubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="cancelsubscription-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|
|» id|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## reactivateSubscription

<a id="opIdreactivateSubscription"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /subscription/{id}/reactivate \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /subscription/{id}/reactivate HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/subscription/{id}/reactivate',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/subscription/{id}/reactivate',
{
  method: 'PUT',

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/subscription/{id}/reactivate',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/subscription/{id}/reactivate', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/subscription/{id}/reactivate");
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
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/subscription/{id}/reactivate", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /subscription/{id}/reactivate`

*Reactivate a subscription*

<h3 id="reactivatesubscription-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The ID of a Zuora subscription|

> Example responses

> 200 Response

```json
{
  "success": true,
  "id": "string"
}
```

<h3 id="reactivatesubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="reactivatesubscription-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|
|» id|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## renewSubscription

<a id="opIdrenewSubscription"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /subscription/{id}/renew \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /subscription/{id}/renew HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/subscription/{id}/renew',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/subscription/{id}/renew',
{
  method: 'PUT',

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/subscription/{id}/renew',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/subscription/{id}/renew', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/subscription/{id}/renew");
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
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/subscription/{id}/renew", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /subscription/{id}/renew`

*Renew a subscription*

<h3 id="renewsubscription-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The ID of a Zuora subscription|

> Example responses

> 200 Response

```json
{
  "success": true,
  "id": "string"
}
```

<h3 id="renewsubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="renewsubscription-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|
|» id|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## resumeSubscription

<a id="opIdresumeSubscription"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /subscription/{id}/resume \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /subscription/{id}/resume HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/subscription/{id}/resume',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/subscription/{id}/resume',
{
  method: 'PUT',

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/subscription/{id}/resume',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/subscription/{id}/resume', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/subscription/{id}/resume");
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
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/subscription/{id}/resume", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /subscription/{id}/resume`

*Resume a subscription*

<h3 id="resumesubscription-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The ID of a Zuora subscription|

> Example responses

> 200 Response

```json
{
  "success": true,
  "id": "string"
}
```

<h3 id="resumesubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="resumesubscription-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|
|» id|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## suspendSubscription

<a id="opIdsuspendSubscription"></a>

> Code samples

```shell
# You can also use wget
curl -X PUT /subscription/{id}/suspend \
  -H 'Accept: application/json' \
  -H 'Authorization: Bearer {access-token}'

```

```http
PUT /subscription/{id}/suspend HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

$.ajax({
  url: '/subscription/{id}/suspend',
  method: 'put',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json',
  'Authorization':'Bearer {access-token}'

};

fetch('/subscription/{id}/suspend',
{
  method: 'PUT',

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
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/subscription/{id}/suspend',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json',
  'Authorization': 'Bearer {access-token}'
}

r = requests.put('/subscription/{id}/suspend', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/subscription/{id}/suspend");
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
        "Accept": []string{"application/json"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("PUT", "/subscription/{id}/suspend", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`PUT /subscription/{id}/suspend`

*Suspend a subscription*

<h3 id="suspendsubscription-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The ID of a Zuora subscription|

> Example responses

> 200 Response

```json
{
  "success": true,
  "id": "string"
}
```

<h3 id="suspendsubscription-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="suspendsubscription-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|
|» id|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

<h1 id="Subscription-Suite-API-translation">translation</h1>

Fetch static and dynamic translations for UI elements and the product catalog

## getTranslations

<a id="opIdgetTranslations"></a>

> Code samples

```shell
# You can also use wget
curl -X GET /translation?lang=string \
  -H 'Accept: application/json'

```

```http
GET /translation?lang=string HTTP/1.1

Accept: application/json

```

```javascript
var headers = {
  'Accept':'application/json'

};

$.ajax({
  url: '/translation',
  method: 'get',
  data: '?lang=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');

const headers = {
  'Accept':'application/json'

};

fetch('/translation?lang=string',
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

result = RestClient.get '/translation',
  params: {
  'lang' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/translation', params={
  'lang': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/translation?lang=string");
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
    req, err := http.NewRequest("GET", "/translation", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`GET /translation`

*Get static translations for a certain language*

<h3 id="gettranslations-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|lang|query|string|true|Language for translations|

> Example responses

> 200 Response

```json
[
  {
    "key": "string",
    "translation": "string"
  }
]
```

<h3 id="gettranslations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="gettranslations-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» key|string|false|none|none|
|» translation|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## getDynamicTranslations

<a id="opIdgetDynamicTranslations"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /translation/dynamic?lang=string \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /translation/dynamic?lang=string HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/translation/dynamic',
  method: 'post',
  data: '?lang=string',
  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '[
  "string"
]';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/translation/dynamic?lang=string',
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

result = RestClient.post '/translation/dynamic',
  params: {
  'lang' => 'string'
}, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Content-Type': 'application/json',
  'Accept': 'application/json'
}

r = requests.post('/translation/dynamic', params={
  'lang': 'string'
}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/translation/dynamic?lang=string");
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
    req, err := http.NewRequest("POST", "/translation/dynamic", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /translation/dynamic`

*Get dynamic translations for the keys specified in the request body*

> Body parameter

```json
[
  "string"
]
```

<h3 id="getdynamictranslations-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|lang|query|string|true|Language for translations|
|body|body|array[string]|true|none|

> Example responses

> 200 Response

```json
[
  {
    "key": "string",
    "translation": "string"
  }
]
```

<h3 id="getdynamictranslations-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="getdynamictranslations-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» key|string|false|none|none|
|» translation|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="Subscription-Suite-API-voucher">voucher</h1>

Consume voucher codes and provide discounts

## initVoucherCode

<a id="opIdinitVoucherCode"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /voucher-code/{code}/init \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /voucher-code/{code}/init HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/voucher-code/{code}/init',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "pageId": "string",
  "userId": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/voucher-code/{code}/init',
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

result = RestClient.post '/voucher-code/{code}/init',
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

r = requests.post('/voucher-code/{code}/init', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/voucher-code/{code}/init");
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
    req, err := http.NewRequest("POST", "/voucher-code/{code}/init", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /voucher-code/{code}/init`

*Initialize a voucher code and block it for a certain user in case of a single use code*

> Body parameter

```json
{
  "pageId": "string",
  "userId": 0
}
```

<h3 id="initvouchercode-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|code|path|string|true|The voucher code that should be applied|
|body|body|object|true|none|
|» pageId|body|string|false|none|
|» userId|body|integer|false|none|

> Example responses

> 200 Response

```json
{
  "discountRatePlanId": 0,
  "success": true
}
```

<h3 id="initvouchercode-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|

<h3 id="initvouchercode-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» discountRatePlanId|integer|false|none|none|
|» success|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## consumeVoucherCode

<a id="opIdconsumeVoucherCode"></a>

> Code samples

```shell
# You can also use wget
curl -X POST /voucher-code/{code}/consume \
  -H 'Content-Type: application/json' \
  -H 'Accept: application/json'

```

```http
POST /voucher-code/{code}/consume HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```javascript
var headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

$.ajax({
  url: '/voucher-code/{code}/consume',
  method: 'post',

  headers: headers,
  success: function(data) {
    console.log(JSON.stringify(data));
  }
})

```

```javascript--nodejs
const fetch = require('node-fetch');
const inputBody = '{
  "pageId": "string",
  "userId": 0
}';
const headers = {
  'Content-Type':'application/json',
  'Accept':'application/json'

};

fetch('/voucher-code/{code}/consume',
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

result = RestClient.post '/voucher-code/{code}/consume',
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

r = requests.post('/voucher-code/{code}/consume', params={

}, headers = headers)

print r.json()

```

```java
URL obj = new URL("/voucher-code/{code}/consume");
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
    req, err := http.NewRequest("POST", "/voucher-code/{code}/consume", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

`POST /voucher-code/{code}/consume`

*Confirm and consume a voucher code*

> Body parameter

```json
{
  "pageId": "string",
  "userId": 0
}
```

<h3 id="consumevouchercode-parameters">Parameters</h3>

|Parameter|In|Type|Required|Description|
|---|---|---|---|---|
|code|path|string|true|The voucher code that should be applied|
|body|body|object|true|none|
|» pageId|body|string|false|none|
|» userId|body|integer|false|none|

> Example responses

> 200 Response

```json
{
  "discountRatePlanId": 0,
  "success": true
}
```

<h3 id="consumevouchercode-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|

<h3 id="consumevouchercode-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» discountRatePlanId|integer|false|none|none|
|» success|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocScontact">Contact</h2>

<a id="schemacontact"></a>

```json
{
  "address1": "string",
  "address2": "string",
  "city": "string",
  "country": "string",
  "county": "string",
  "fax": "string",
  "firstName": "string",
  "lastName": "string",
  "state": "string",
  "taxRegion": "string",
  "workEmail": "string",
  "workPhone": "string",
  "zipCode": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|address1|string|false|none|none|
|address2|string|false|none|none|
|city|string|false|none|none|
|country|string|false|none|none|
|county|string|false|none|none|
|fax|string|false|none|none|
|firstName|string|false|none|none|
|lastName|string|false|none|none|
|state|string|false|none|none|
|taxRegion|string|false|none|none|
|workEmail|string|false|none|none|
|workPhone|string|false|none|none|
|zipCode|string|false|none|none|

<h2 id="tocSpaymentmethod">PaymentMethod</h2>

<a id="schemapaymentmethod"></a>

```json
{
  "id": "string",
  "type": "string",
  "creditCardNumber": "string",
  "creditCardHolder": "string",
  "creditCardExpirationMonth": 0,
  "creditCardExpirationYear": 0,
  "iban": "string",
  "bankAccountHolder": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|type|string|false|none|none|
|creditCardNumber|string|false|none|none|
|creditCardHolder|string|false|none|none|
|creditCardExpirationMonth|number|false|none|none|
|creditCardExpirationYear|number|false|none|none|
|iban|string|false|none|none|
|bankAccountHolder|string|false|none|none|

<h2 id="tocSproduct">Product</h2>

<a id="schemaproduct"></a>

```json
{
  "id": "string",
  "type": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|type|string|false|none|none|

<h2 id="tocSrateplan">RatePlan</h2>

<a id="schemarateplan"></a>

```json
{
  "id": "string",
  "type": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|type|string|false|none|none|

<h2 id="tocSsubscribeoption">SubscribeOption</h2>

<a id="schemasubscribeoption"></a>

```json
{
  "ratePlan": {
    "id": 0,
    "quantity": 0
  },
  "charges": [
    {
      "id": 0,
      "quantity": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ratePlan|object|false|none|none|
|» id|integer|false|none|none|
|» quantity|integer|false|none|none|
|charges|[object]|false|none|none|
|» id|integer|false|none|none|
|» quantity|integer|false|none|none|

<h2 id="tocSsubscribeoptionwithprice">SubscribeOptionWithPrice</h2>

<a id="schemasubscribeoptionwithprice"></a>

```json
{
  "ratePlan": {
    "id": 0,
    "quantity": 0,
    "price": 0,
    "tax": 0,
    "total": 0
  },
  "charges": [
    {
      "id": 0,
      "quantity": 0,
      "price": 0,
      "tax": 0,
      "total": 0
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|ratePlan|object|false|none|none|
|» id|integer|false|none|none|
|» quantity|integer|false|none|none|
|» price|number|false|none|none|
|» tax|number|false|none|none|
|» total|number|false|none|none|
|charges|[object]|false|none|none|
|» id|integer|false|none|none|
|» quantity|integer|false|none|none|
|» price|number|false|none|none|
|» tax|number|false|none|none|
|» total|number|false|none|none|

