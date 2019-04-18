---
title: Subscription Suite API
language_tabs:
  - go: Go
  - http: HTTP
  - ruby: Ruby
  - python: Python
toc_footers: []
includes: []
search: false
highlight_theme: darkula
headingLevel: 2

---

<h1 id="subscription-suite-api">Subscription Suite API v1.0.0</h1>

> Scroll down for code samples, example requests and responses. Select a language for code samples from the tabs above or the mobile navigation menu.

This is the API that is used by the Subscription Suite Angular 6 frontend components. You can find out more about Subscription Suite at [https://www.subscription-suite.com](https://www.subscription-suite.com).

Email: <a href="mailto:hello@keylight.de">Support</a> 

# Authentication

- HTTP Authentication, scheme: bearer 

* API Key (cookieAuth)
    - Parameter Name: **user**, in: cookie. 

<h1 id="subscription-suite-api-account">account</h1>

Manage data related to Zuora billing accounts

## Get summarized information about an account, in particular name and the address information

<a id="opIdgetAccount"></a>

> Code samples

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

```http
GET /account HTTP/1.1

Accept: application/json

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

`GET /account`

> Example responses

> 200 Response

```json
{
  "company_name": "string",
  "currency": "string",
  "first_name": "string",
  "last_name": "string",
  "street": "string",
  "additional_info": "string",
  "zip_code": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "email": "string",
  "phone": "string",
  "vat_id": "string",
  "has_billing_address": true,
  "is_company": true,
  "billing_first_name": "string",
  "billing_last_name": "string",
  "billing_street": "string",
  "billing_additional_info": "string",
  "billing_zip_code": "string",
  "billing_city": "string",
  "billing_country": "string",
  "billing_email": "string",
  "billing_phone": "string"
}
```

<h3 id="get-summarized-information-about-an-account,-in-particular-name-and-the-address-information-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Account](#schemaaccount)|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## Update an existing account

<a id="opIdupdateAccount"></a>

> Code samples

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

```http
PUT /account HTTP/1.1

Content-Type: application/json
Accept: application/json

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

`PUT /account`

> Body parameter

```json
{
  "company_name": "string",
  "currency": "string",
  "first_name": "string",
  "last_name": "string",
  "street": "string",
  "additional_info": "string",
  "zip_code": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "email": "string",
  "phone": "string",
  "vat_id": "string",
  "has_billing_address": true,
  "is_company": true,
  "billing_first_name": "string",
  "billing_last_name": "string",
  "billing_street": "string",
  "billing_additional_info": "string",
  "billing_zip_code": "string",
  "billing_city": "string",
  "billing_country": "string",
  "billing_email": "string",
  "billing_phone": "string"
}
```

<h3 id="update-an-existing-account-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[Account](#schemaaccount)|true|none|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="update-an-existing-account-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="update-an-existing-account-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## Get the accounts payment method

<a id="opIdaccountPaymentMethod"></a>

> Code samples

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
    req, err := http.NewRequest("GET", "/account/payment-method", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /account/payment-method HTTP/1.1

Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/account/payment-method',
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

r = requests.get('/account/payment-method', params={

}, headers = headers)

print r.json()

```

`GET /account/payment-method`

> Example responses

> 200 Response

```json
{
  "id": "string",
  "type": "string",
  "data": {}
}
```

<h3 id="get-the-accounts-payment-method-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|success|[AccountPaymentMethod](#schemaaccountpaymentmethod)|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## Update the Accounts payment method

<a id="opIdupdateAccountPaymentMethod"></a>

> Code samples

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
    req, err := http.NewRequest("PUT", "/account/payment-method", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
PUT /account/payment-method HTTP/1.1

Content-Type: application/json
Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Content-Type' => 'application/json',
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.put '/account/payment-method',
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

r = requests.put('/account/payment-method', params={

}, headers = headers)

print r.json()

```

`PUT /account/payment-method`

> Body parameter

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

<h3 id="update-the-accounts-payment-method-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|body|body|[PaymentMethod](#schemapaymentmethod)|true|none|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="update-the-accounts-payment-method-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="update-the-accounts-payment-method-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## Get posted invoices for a user

<a id="opIdgetInvoices"></a>

> Code samples

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

```http
GET /account/invoice HTTP/1.1

Accept: application/json

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

`GET /account/invoice`

> Example responses

> 200 Response

```json
[
  {
    "payment_amount": 0,
    "invoice_date": "2019-04-18",
    "due_date": "2019-04-18",
    "tax_amount": 0,
    "amount": 0,
    "balance": 0,
    "amount_without_tax": 0,
    "invoice_number": "string",
    "id": "string"
  }
]
```

<h3 id="get-posted-invoices-for-a-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="get-posted-invoices-for-a-user-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Invoice](#schemainvoice)]|false|none|none|
|» payment_amount|number|false|none|none|
|» invoice_date|string(date)|false|none|none|
|» due_date|string(date)|false|none|none|
|» tax_amount|number|false|none|none|
|» amount|number|false|none|none|
|» balance|number|false|none|none|
|» amount_without_tax|number|false|none|none|
|» invoice_number|string|false|none|none|
|» id|string|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## Get Invoice for Account by InvoiceId

> Code samples

```go
package main

import (
       "bytes"
       "net/http"
)

func main() {

    headers := map[string][]string{
        "Accept": []string{"application/pdf"},
        "Authorization": []string{"Bearer {access-token}"},
        
    }

    data := bytes.NewBuffer([]byte{jsonReq})
    req, err := http.NewRequest("GET", "/account/invoice/{invoiceId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /account/invoice/{invoiceId} HTTP/1.1

Accept: application/pdf

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/pdf',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/account/invoice/{invoiceId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/pdf',
  'Authorization': 'Bearer {access-token}'
}

r = requests.get('/account/invoice/{invoiceId}', params={

}, headers = headers)

print r.json()

```

`GET /account/invoice/{invoiceId}`

<h3 id="get-invoice-for-account-by-invoiceid-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|invoiceId|path|string|true|Id of the wanted invoice|

> Example responses

> 200 Response

<h3 id="get-invoice-for-account-by-invoiceid-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|string|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## Get subscriptions for a user

<a id="opIdgetSubscriptions"></a>

> Code samples

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

```http
GET /account/subscription HTTP/1.1

Accept: application/json

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

`GET /account/subscription`

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "name": "string",
    "description": "string",
    "feature_list": "string",
    "effective_start_date": "string",
    "effective_end_date": "string",
    "different_quantities_allowed": 0,
    "different_quantities_allowed_for_charge": 0,
    "purchasable_by_customer": 0,
    "purchasable_by_partner": 0,
    "purchasable_by_sales": 0,
    "multiple_subscriptions_allowed": 0,
    "tenant_id": 0,
    "subscription_type": "string",
    "renewal_type": "string",
    "term": 0,
    "renewal_term": 0,
    "is_auto_renew": 0,
    "cancel_behaviour": 0,
    "quantity_upgrade_behaviour": 0,
    "quantity_downgrade_behaviour": 0,
    "upgrade_behaviour": 0,
    "downgrade_behaviour": 0,
    "new_subscribe_mode": 0,
    "add_on_mode": 0,
    "has_contact_us_link": 0,
    "trusted_html": "string",
    "quantity_level": 0,
    "price_level": 0,
    "cancel_period": 0,
    "generated_id": "string",
    "cancel_mode": 0,
    "quantity_upgrade_mode": 0,
    "quantity_downgrade_mode": 0,
    "upgrade_mode": 0,
    "downgrade_mode": 0,
    "categories": [],
    "add_ons": [],
    "change_options": [],
    "subscription": {
      "id": "string",
      "account_id": "string",
      "account_number": "string",
      "account_name": "string",
      "invoice_owner_account_id": "string",
      "invoice_owner_account_number": "string",
      "invoice_owner_account_name": "string",
      "subscription_number": "string",
      "term_type": "string",
      "invoice_separately": true,
      "contract_effective_date": "string",
      "service_activation_date": "string",
      "customer_acceptance_date": "string",
      "subscription_start_date": "string",
      "term_start_date": "string",
      "term_end_date": "string",
      "initial_term": 0,
      "initial_term_period_type": "string",
      "current_term": 0,
      "current_term_period_type": "string",
      "auto_renew": true,
      "renewal_setting": "string",
      "renewal_term": 0,
      "renewal_term_period_type": "string",
      "contracted_mrr": 0,
      "total_contracted_value": 0,
      "status": "string",
      "rate_plans": [
        {
          "id": "string",
          "product_id": "string",
          "product_name": "string",
          "product_sku": "string",
          "product_rate_plan_id": "string",
          "rate_plan_name": "string",
          "suite_product_id": "string",
          "suite_product_uuid": "string",
          "rate_plan_charges": [
            {
              "id": "string",
              "original_charge_id": "string",
              "product_rate_plan_charge_id": "string",
              "number": "string",
              "name": "string",
              "type": "string",
              "model": "string",
              "version": 0,
              "pricing_summary": "string",
              "price_change_option": "string",
              "price_increase_percentage": 0,
              "currency": "string",
              "price": 0,
              "discount_apply_details": [],
              "billing_day": "string",
              "list_price_base": "string",
              "billing_period": "string",
              "billing_timing": "string",
              "billing_period_alignment": "string",
              "quantity": 0,
              "segment": 0,
              "effective_start_date": "string",
              "effective_end_date": "string",
              "processed_through_date": "string",
              "charged_through_date": "string",
              "done": true,
              "trigger_event": "string",
              "end_date_condition": "string",
              "mrr": 0,
              "dmrc": 0,
              "tcv": 0,
              "dtcv": 0,
              "description": "string"
            }
          ],
          "subscription_product_features": [
            {
              "id": "string",
              "name": "string",
              "feature_code": "string",
              "description": "string"
            }
          ]
        }
      ],
      "latest_rate_plans": [
        {
          "id": "string",
          "product_id": "string",
          "product_name": "string",
          "product_sku": "string",
          "product_rate_plan_id": "string",
          "rate_plan_name": "string",
          "suite_product_id": "string",
          "suite_product_uuid": "string",
          "rate_plan_charges": [
            {
              "id": "string",
              "original_charge_id": "string",
              "product_rate_plan_charge_id": "string",
              "number": "string",
              "name": "string",
              "type": "string",
              "model": "string",
              "version": 0,
              "pricing_summary": "string",
              "price_change_option": "string",
              "price_increase_percentage": 0,
              "currency": "string",
              "price": 0,
              "discount_apply_details": [],
              "billing_day": "string",
              "list_price_base": "string",
              "billing_period": "string",
              "billing_timing": "string",
              "billing_period_alignment": "string",
              "quantity": 0,
              "segment": 0,
              "effective_start_date": "string",
              "effective_end_date": "string",
              "processed_through_date": "string",
              "charged_through_date": "string",
              "done": true,
              "trigger_event": "string",
              "end_date_condition": "string",
              "mrr": 0,
              "dmrc": 0,
              "tcv": 0,
              "dtcv": 0,
              "description": "string"
            }
          ],
          "subscription_product_features": [
            {
              "id": "string",
              "name": "string",
              "feature_code": "string",
              "description": "string"
            }
          ]
        }
      ],
      "current_end_date": "2019-04-18"
    },
    "quantity": 0,
    "rate_plans": [
      {
        "id": "string",
        "product_id": "string",
        "product_name": "string",
        "product_sku": "string",
        "product_rate_plan_id": "string",
        "rate_plan_name": "string",
        "suite_product_id": "string",
        "suite_product_uuid": "string",
        "rate_plan_charges": [
          {
            "id": "string",
            "original_charge_id": "string",
            "product_rate_plan_charge_id": "string",
            "number": "string",
            "name": "string",
            "type": "string",
            "model": "string",
            "version": 0,
            "pricing_summary": "string",
            "price_change_option": "string",
            "price_increase_percentage": 0,
            "currency": "string",
            "price": 0,
            "discount_apply_details": [],
            "billing_day": "string",
            "list_price_base": "string",
            "billing_period": "string",
            "billing_timing": "string",
            "billing_period_alignment": "string",
            "quantity": 0,
            "segment": 0,
            "effective_start_date": "string",
            "effective_end_date": "string",
            "processed_through_date": "string",
            "charged_through_date": "string",
            "done": true,
            "trigger_event": "string",
            "end_date_condition": "string",
            "mrr": 0,
            "dmrc": 0,
            "tcv": 0,
            "dtcv": 0,
            "description": "string"
          }
        ],
        "subscription_product_features": [
          {
            "id": "string",
            "name": "string",
            "feature_code": "string",
            "description": "string"
          }
        ]
      }
    ],
    "uuid": "string"
  }
]
```

<h3 id="get-subscriptions-for-a-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="get-subscriptions-for-a-user-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SuiteProduct](#schemasuiteproduct)]|false|none|none|
|» id|number|true|none|none|
|» name|string|true|none|none|
|» description|string|true|none|none|
|» feature_list|string|true|none|none|
|» effective_start_date|string|true|none|none|
|» effective_end_date|string|true|none|none|
|» different_quantities_allowed|number|true|none|none|
|» different_quantities_allowed_for_charge|number|true|none|none|
|» purchasable_by_customer|number|true|none|none|
|» purchasable_by_partner|number|true|none|none|
|» purchasable_by_sales|number|true|none|none|
|» multiple_subscriptions_allowed|number|true|none|none|
|» tenant_id|number|true|none|none|
|» subscription_type|string|true|none|none|
|» renewal_type|string|true|none|none|
|» term|number|true|none|none|
|» renewal_term|number|true|none|none|
|» is_auto_renew|number|true|none|none|
|» cancel_behaviour|number|true|none|none|
|» quantity_upgrade_behaviour|number|true|none|none|
|» quantity_downgrade_behaviour|number|true|none|none|
|» upgrade_behaviour|number|true|none|none|
|» downgrade_behaviour|number|true|none|none|
|» new_subscribe_mode|number|true|none|none|
|» add_on_mode|number|true|none|none|
|» has_contact_us_link|number|true|none|none|
|» trusted_html|string|true|none|none|
|» quantity_level|number|true|none|none|
|» price_level|number|true|none|none|
|» cancel_period|number|true|none|none|
|» generated_id|string|true|none|none|
|» cancel_mode|number|true|none|none|
|» quantity_upgrade_mode|number|true|none|none|
|» quantity_downgrade_mode|number|true|none|none|
|» upgrade_mode|number|true|none|none|
|» downgrade_mode|number|true|none|none|
|» categories|array|true|none|none|
|» add_ons|array|true|none|none|
|» change_options|array|true|none|none|
|» subscription|object|true|none|none|
|»» id|string|true|none|none|
|»» account_id|string|true|none|none|
|»» account_number|string|true|none|none|
|»» account_name|string|true|none|none|
|»» invoice_owner_account_id|string|true|none|none|
|»» invoice_owner_account_number|string|true|none|none|
|»» invoice_owner_account_name|string|true|none|none|
|»» subscription_number|string|true|none|none|
|»» term_type|string|true|none|none|
|»» invoice_separately|boolean|true|none|none|
|»» contract_effective_date|string|true|none|none|
|»» service_activation_date|string|true|none|none|
|»» customer_acceptance_date|string|true|none|none|
|»» subscription_start_date|string|true|none|none|
|»» term_start_date|string|true|none|none|
|»» term_end_date|string|true|none|none|
|»» initial_term|number|true|none|none|
|»» initial_term_period_type|string|true|none|none|
|»» current_term|number|true|none|none|
|»» current_term_period_type|string|true|none|none|
|»» auto_renew|boolean|true|none|none|
|»» renewal_setting|string|true|none|none|
|»» renewal_term|number|true|none|none|
|»» renewal_term_period_type|string|true|none|none|
|»» contracted_mrr|number|true|none|none|
|»» total_contracted_value|number|true|none|none|
|»» status|string|true|none|none|
|»» rate_plans|[[AccountRatePlan](#schemaaccountrateplan)]|true|none|none|
|»»» id|string|false|none|none|
|»»» product_id|string|false|none|none|
|»»» product_name|string|false|none|none|
|»»» product_sku|string|false|none|none|
|»»» product_rate_plan_id|string|false|none|none|
|»»» rate_plan_name|string|false|none|none|
|»»» suite_product_id|string|false|none|none|
|»»» suite_product_uuid|string|false|none|none|
|»»» rate_plan_charges|[[RatePlanCharge](#schemarateplancharge)]|false|none|none|
|»»»» id|string|false|none|none|
|»»»» original_charge_id|string|false|none|none|
|»»»» product_rate_plan_charge_id|string|false|none|none|
|»»»» number|string|false|none|none|
|»»»» name|string|false|none|none|
|»»»» type|string|false|none|none|
|»»»» model|string|false|none|none|
|»»»» version|number|false|none|none|
|»»»» pricing_summary|string|false|none|none|
|»»»» price_change_option|string|false|none|none|
|»»»» price_increase_percentage|number|false|none|none|
|»»»» currency|string|false|none|none|
|»»»» price|number|false|none|none|
|»»»» discount_apply_details|array|false|none|none|
|»»»» billing_day|string|false|none|none|
|»»»» list_price_base|string|false|none|none|
|»»»» billing_period|string|false|none|none|
|»»»» billing_timing|string|false|none|none|
|»»»» billing_period_alignment|string|false|none|none|
|»»»» quantity|number|false|none|none|
|»»»» segment|number|false|none|none|
|»»»» effective_start_date|string|false|none|none|
|»»»» effective_end_date|string|false|none|none|
|»»»» processed_through_date|string|false|none|none|
|»»»» charged_through_date|string|false|none|none|
|»»»» done|boolean|false|none|none|
|»»»» trigger_event|string|false|none|none|
|»»»» end_date_condition|string|false|none|none|
|»»»» mrr|number|false|none|none|
|»»»» dmrc|number|false|none|none|
|»»»» tcv|number|false|none|none|
|»»»» dtcv|number|false|none|none|
|»»»» description|string|false|none|none|
|»»» subscription_product_features|[[SubscriptionProductFeature](#schemasubscriptionproductfeature)]|false|none|none|
|»»»» id|string|false|none|none|
|»»»» name|string|false|none|none|
|»»»» feature_code|string|false|none|none|
|»»»» description|string|false|none|none|
|»»» latest_rate_plans|[[AccountRatePlan](#schemaaccountrateplan)]|false|none|none|
|»»» current_end_date|string(date)|true|none|none|
|»» quantity|number|true|none|none|
|»» rate_plans|[[AccountRatePlan](#schemaaccountrateplan)]|true|none|none|
|»» uuid|string|true|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## Validate a VAT ID

<a id="opIdvalidateVatId"></a>

> Code samples

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

```http
GET /account/vat-validate/{vatId} HTTP/1.1

Accept: application/json

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

`GET /account/vat-validate/{vatId}`

<h3 id="validate-a-vat-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|vatId|path|string|true|VAT ID that needs to be checked|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="validate-a-vat-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="validate-a-vat-id-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Get Rate Plans

<a id="opIdratePlans"></a>

> Code samples

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
    req, err := http.NewRequest("GET", "/account/rate-plan", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /account/rate-plan HTTP/1.1

Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json',
  'Authorization' => 'Bearer {access-token}'
}

result = RestClient.get '/account/rate-plan',
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

r = requests.get('/account/rate-plan', params={

}, headers = headers)

print r.json()

```

`GET /account/rate-plan`

> Example responses

> 200 Response

```json
[
  {
    "subscription": {
      "id": "string",
      "account_id": "string",
      "account_number": "string",
      "account_name": "string",
      "invoice_owner_account_id": "string",
      "invoice_owner_account_number": "string",
      "invoice_owner_account_name": "string",
      "subscription_number": "string",
      "term_type": "string",
      "invoice_separately": true,
      "contract_effective_date": "string",
      "service_activation_date": "string",
      "customer_acceptance_date": "string",
      "subscription_start_date": "string",
      "term_start_date": "string",
      "term_end_date": "string",
      "initial_term": 0,
      "initial_term_period_type": "string",
      "current_term": 0,
      "current_term_period_type": "string",
      "auto_renew": true,
      "renewal_setting": "string",
      "renewal_term": 0,
      "renewal_term_period_type": "string",
      "contracted_mrr": 0,
      "total_contracted_value": 0,
      "status": "string",
      "rate_plans": [
        {
          "id": "string",
          "product_id": "string",
          "product_name": "string",
          "product_sku": "string",
          "product_rate_plan_id": "string",
          "rate_plan_name": "string",
          "suite_product_id": "string",
          "suite_product_uuid": "string",
          "rate_plan_charges": [
            {
              "id": "string",
              "original_charge_id": "string",
              "product_rate_plan_charge_id": "string",
              "number": "string",
              "name": "string",
              "type": "string",
              "model": "string",
              "version": 0,
              "pricing_summary": "string",
              "price_change_option": "string",
              "price_increase_percentage": 0,
              "currency": "string",
              "price": 0,
              "discount_apply_details": [],
              "billing_day": "string",
              "list_price_base": "string",
              "billing_period": "string",
              "billing_timing": "string",
              "billing_period_alignment": "string",
              "quantity": 0,
              "segment": 0,
              "effective_start_date": "string",
              "effective_end_date": "string",
              "processed_through_date": "string",
              "charged_through_date": "string",
              "done": true,
              "trigger_event": "string",
              "end_date_condition": "string",
              "mrr": 0,
              "dmrc": 0,
              "tcv": 0,
              "dtcv": 0,
              "description": "string"
            }
          ],
          "subscription_product_features": [
            {
              "id": "string",
              "name": "string",
              "feature_code": "string",
              "description": "string"
            }
          ]
        }
      ],
      "latest_rate_plans": [
        {
          "id": "string",
          "product_id": "string",
          "product_name": "string",
          "product_sku": "string",
          "product_rate_plan_id": "string",
          "rate_plan_name": "string",
          "suite_product_id": "string",
          "suite_product_uuid": "string",
          "rate_plan_charges": [
            {
              "id": "string",
              "original_charge_id": "string",
              "product_rate_plan_charge_id": "string",
              "number": "string",
              "name": "string",
              "type": "string",
              "model": "string",
              "version": 0,
              "pricing_summary": "string",
              "price_change_option": "string",
              "price_increase_percentage": 0,
              "currency": "string",
              "price": 0,
              "discount_apply_details": [],
              "billing_day": "string",
              "list_price_base": "string",
              "billing_period": "string",
              "billing_timing": "string",
              "billing_period_alignment": "string",
              "quantity": 0,
              "segment": 0,
              "effective_start_date": "string",
              "effective_end_date": "string",
              "processed_through_date": "string",
              "charged_through_date": "string",
              "done": true,
              "trigger_event": "string",
              "end_date_condition": "string",
              "mrr": 0,
              "dmrc": 0,
              "tcv": 0,
              "dtcv": 0,
              "description": "string"
            }
          ],
          "subscription_product_features": [
            {
              "id": "string",
              "name": "string",
              "feature_code": "string",
              "description": "string"
            }
          ]
        }
      ],
      "current_end_date": "2019-04-18"
    },
    "id": "string",
    "product_id": "string",
    "product_name": "string",
    "product_sku": "string",
    "product_rate_plan_id": "string",
    "rate_plan_name": "string",
    "suite_product_id": "string",
    "suite_product_uuid": "string",
    "rate_plan_charges": [
      {
        "id": "string",
        "original_charge_id": "string",
        "product_rate_plan_charge_id": "string",
        "number": "string",
        "name": "string",
        "type": "string",
        "model": "string",
        "version": 0,
        "pricing_summary": "string",
        "price_change_option": "string",
        "price_increase_percentage": 0,
        "currency": "string",
        "price": 0,
        "discount_apply_details": [],
        "billing_day": "string",
        "list_price_base": "string",
        "billing_period": "string",
        "billing_timing": "string",
        "billing_period_alignment": "string",
        "quantity": 0,
        "segment": 0,
        "effective_start_date": "string",
        "effective_end_date": "string",
        "processed_through_date": "string",
        "charged_through_date": "string",
        "done": true,
        "trigger_event": "string",
        "end_date_condition": "string",
        "mrr": 0,
        "dmrc": 0,
        "tcv": 0,
        "dtcv": 0,
        "description": "string"
      }
    ],
    "subscription_product_features": [
      {
        "id": "string",
        "name": "string",
        "feature_code": "string",
        "description": "string"
      }
    ]
  }
]
```

<h3 id="get-rate-plans-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="get-rate-plans-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[SubscriptionAndRatePlan](#schemasubscriptionandrateplan)]|false|none|none|
|» subscription|object|false|none|none|
|»» id|string|true|none|none|
|»» account_id|string|true|none|none|
|»» account_number|string|true|none|none|
|»» account_name|string|true|none|none|
|»» invoice_owner_account_id|string|true|none|none|
|»» invoice_owner_account_number|string|true|none|none|
|»» invoice_owner_account_name|string|true|none|none|
|»» subscription_number|string|true|none|none|
|»» term_type|string|true|none|none|
|»» invoice_separately|boolean|true|none|none|
|»» contract_effective_date|string|true|none|none|
|»» service_activation_date|string|true|none|none|
|»» customer_acceptance_date|string|true|none|none|
|»» subscription_start_date|string|true|none|none|
|»» term_start_date|string|true|none|none|
|»» term_end_date|string|true|none|none|
|»» initial_term|number|true|none|none|
|»» initial_term_period_type|string|true|none|none|
|»» current_term|number|true|none|none|
|»» current_term_period_type|string|true|none|none|
|»» auto_renew|boolean|true|none|none|
|»» renewal_setting|string|true|none|none|
|»» renewal_term|number|true|none|none|
|»» renewal_term_period_type|string|true|none|none|
|»» contracted_mrr|number|true|none|none|
|»» total_contracted_value|number|true|none|none|
|»» status|string|true|none|none|
|»» rate_plans|[[AccountRatePlan](#schemaaccountrateplan)]|true|none|none|
|»»» id|string|false|none|none|
|»»» product_id|string|false|none|none|
|»»» product_name|string|false|none|none|
|»»» product_sku|string|false|none|none|
|»»» product_rate_plan_id|string|false|none|none|
|»»» rate_plan_name|string|false|none|none|
|»»» suite_product_id|string|false|none|none|
|»»» suite_product_uuid|string|false|none|none|
|»»» rate_plan_charges|[[RatePlanCharge](#schemarateplancharge)]|false|none|none|
|»»»» id|string|false|none|none|
|»»»» original_charge_id|string|false|none|none|
|»»»» product_rate_plan_charge_id|string|false|none|none|
|»»»» number|string|false|none|none|
|»»»» name|string|false|none|none|
|»»»» type|string|false|none|none|
|»»»» model|string|false|none|none|
|»»»» version|number|false|none|none|
|»»»» pricing_summary|string|false|none|none|
|»»»» price_change_option|string|false|none|none|
|»»»» price_increase_percentage|number|false|none|none|
|»»»» currency|string|false|none|none|
|»»»» price|number|false|none|none|
|»»»» discount_apply_details|array|false|none|none|
|»»»» billing_day|string|false|none|none|
|»»»» list_price_base|string|false|none|none|
|»»»» billing_period|string|false|none|none|
|»»»» billing_timing|string|false|none|none|
|»»»» billing_period_alignment|string|false|none|none|
|»»»» quantity|number|false|none|none|
|»»»» segment|number|false|none|none|
|»»»» effective_start_date|string|false|none|none|
|»»»» effective_end_date|string|false|none|none|
|»»»» processed_through_date|string|false|none|none|
|»»»» charged_through_date|string|false|none|none|
|»»»» done|boolean|false|none|none|
|»»»» trigger_event|string|false|none|none|
|»»»» end_date_condition|string|false|none|none|
|»»»» mrr|number|false|none|none|
|»»»» dmrc|number|false|none|none|
|»»»» tcv|number|false|none|none|
|»»»» dtcv|number|false|none|none|
|»»»» description|string|false|none|none|
|»»» subscription_product_features|[[SubscriptionProductFeature](#schemasubscriptionproductfeature)]|false|none|none|
|»»»» id|string|false|none|none|
|»»»» name|string|false|none|none|
|»»»» feature_code|string|false|none|none|
|»»»» description|string|false|none|none|
|»»» latest_rate_plans|[[AccountRatePlan](#schemaaccountrateplan)]|false|none|none|
|»»» current_end_date|string(date)|true|none|none|
|»» id|string|false|none|none|
|»» product_id|string|false|none|none|
|»» product_name|string|false|none|none|
|»» product_sku|string|false|none|none|
|»» product_rate_plan_id|string|false|none|none|
|»» rate_plan_name|string|false|none|none|
|»» suite_product_id|string|false|none|none|
|»» suite_product_uuid|string|false|none|none|
|»» rate_plan_charges|[[RatePlanCharge](#schemarateplancharge)]|false|none|none|
|»» subscription_product_features|[[SubscriptionProductFeature](#schemasubscriptionproductfeature)]|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

<h1 id="subscription-suite-api-payment-method">payment-method</h1>

Creating and updating payment methods. Helpers to deal with Paypal and Zuora integration.

## Get a payment method by Zuora Id

<a id="opIdgetPaymentMethodById"></a>

> Code samples

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

```http
GET /payment-method/{id} HTTP/1.1

Accept: application/json

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

`GET /payment-method/{id}`

<h3 id="get-a-payment-method-by-zuora-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
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

<h3 id="get-a-payment-method-by-zuora-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[PaymentMethod](#schemapaymentmethod)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## Get the signature to render a Zuora payment page in an iFrame

<a id="opIdgetZuoraPaymentPageSignature"></a>

> Code samples

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

```http
GET /payment-method/{id}/signature HTTP/1.1

Accept: application/json

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

`GET /payment-method/{id}/signature`

<h3 id="get-the-signature-to-render-a-zuora-payment-page-in-an-iframe-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
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

<h3 id="get-the-signature-to-render-a-zuora-payment-page-in-an-iframe-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<h3 id="get-the-signature-to-render-a-zuora-payment-page-in-an-iframe-responseschema">Response Schema</h3>

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

## Get the available payment methods for a certain user type

<a id="opIdgetAvailablePaymentMethods"></a>

> Code samples

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

```http
GET /payment-method/available HTTP/1.1

Accept: application/json

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

`GET /payment-method/available`

<h3 id="get-the-available-payment-methods-for-a-certain-user-type-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
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

<h3 id="get-the-available-payment-methods-for-a-certain-user-type-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="get-the-available-payment-methods-for-a-certain-user-type-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» id|integer|false|none|none|
|» type|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="subscription-suite-api-quote">quote</h1>

Quote acceptance processes with Salesforce integration

## Get quote data from Salesforce

<a id="opIdgetQuote"></a>

> Code samples

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

```http
GET /quote/{id} HTTP/1.1

Accept: application/json

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

`GET /quote/{id}`

<h3 id="get-quote-data-from-salesforce-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
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
  "startDate": "2019-04-18",
  "term": "string",
  "validUntiDate": "2019-04-18",
  "vatId": "string"
}
```

<h3 id="get-quote-data-from-salesforce-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<h3 id="get-quote-data-from-salesforce-responseschema">Response Schema</h3>

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

## Confirm a quote in Salesforce and send it to Zuora

<a id="opIdconfirmQuote"></a>

> Code samples

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

```http
POST /quote/{id} HTTP/1.1

Accept: application/json

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

`POST /quote/{id}`

<h3 id="confirm-a-quote-in-salesforce-and-send-it-to-zuora-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|string|true|The ID of a Salesforce quote|

> Example responses

> 200 Response

```json
{
  "success": true
}
```

<h3 id="confirm-a-quote-in-salesforce-and-send-it-to-zuora-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<h3 id="confirm-a-quote-in-salesforce-and-send-it-to-zuora-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="subscription-suite-api-product-catalog">product-catalog</h1>

Fetching and managing the Zuora product catalog

## Get all Zuora products

<a id="opIdgetProducts"></a>

> Code samples

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

```http
GET /product HTTP/1.1

Accept: application/json

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

`GET /product`

> Example responses

> 200 Response

```json
[
  {
    "id": 0,
    "zuora_id": "string",
    "name": "string",
    "description": "string",
    "feature_list": "string",
    "highlight": "string",
    "effective_start_date": "string",
    "effective_end_date": "string",
    "sku": "string",
    "updated_date": "string",
    "tenant_id": 0
  }
]
```

<h3 id="get-all-zuora-products-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="get-all-zuora-products-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|*anonymous*|[[Product](#schemaproduct)]|false|none|none|
|» id|number|false|none|none|
|» zuora_id|string|false|none|none|
|» name|string|false|none|none|
|» description|string|false|none|none|
|» feature_list|string|false|none|none|
|» highlight|string|false|none|none|
|» effective_start_date|string|false|none|none|
|» effective_end_date|string|false|none|none|
|» sku|string|false|none|none|
|» updated_date|string|false|none|none|
|» tenant_id|number|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Get a Zuora product

<a id="opIddeleteProductById"></a>

> Code samples

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
    req, err := http.NewRequest("DELETE", "/product/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
DELETE /product/{id} HTTP/1.1

Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.delete '/product/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.delete('/product/{id}', params={

}, headers = headers)

print r.json()

```

`DELETE /product/{id}`

<h3 id="get-a-zuora-product-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Subscription Suite product|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "zuora_id": "string",
  "name": "string",
  "description": "string",
  "feature_list": "string",
  "highlight": "string",
  "effective_start_date": "string",
  "effective_end_date": "string",
  "sku": "string",
  "updated_date": "string",
  "tenant_id": 0
}
```

<h3 id="get-a-zuora-product-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Product](#schemaproduct)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## Preview of Cancel Operation

<a id="opIdproductPreviewCancel"></a>

> Code samples

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
    req, err := http.NewRequest("GET", "/product/{id}/preview/cancel", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /product/{id}/preview/cancel HTTP/1.1

Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/product/{id}/preview/cancel',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/product/{id}/preview/cancel', params={

}, headers = headers)

print r.json()

```

`GET /product/{id}/preview/cancel`

<h3 id="preview-of-cancel-operation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Subscription Suite product|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "zuora_id": "string",
  "name": "string",
  "description": "string",
  "feature_list": "string",
  "highlight": "string",
  "effective_start_date": "string",
  "effective_end_date": "string",
  "sku": "string",
  "updated_date": "string",
  "tenant_id": 0
}
```

<h3 id="preview-of-cancel-operation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Product](#schemaproduct)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## Preview of Replace Operation

<a id="opIdproductPreviewReplace"></a>

> Code samples

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
    req, err := http.NewRequest("GET", "/product/{id}/preview/replace/{changeOptionId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /product/{id}/preview/replace/{changeOptionId} HTTP/1.1

Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/product/{id}/preview/replace/{changeOptionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/product/{id}/preview/replace/{changeOptionId}', params={

}, headers = headers)

print r.json()

```

`GET /product/{id}/preview/replace/{changeOptionId}`

<h3 id="preview-of-replace-operation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Subscription Suite product|
|changeOptionId|path|integer|true|The ID of a Subscription Change Option|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "zuora_id": "string",
  "name": "string",
  "description": "string",
  "feature_list": "string",
  "highlight": "string",
  "effective_start_date": "string",
  "effective_end_date": "string",
  "sku": "string",
  "updated_date": "string",
  "tenant_id": 0
}
```

<h3 id="preview-of-replace-operation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Product](#schemaproduct)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## Replace Operation

<a id="opIdproductReplace"></a>

> Code samples

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
    req, err := http.NewRequest("GET", "/product/{id}/replace/{changeOptionId}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /product/{id}/replace/{changeOptionId} HTTP/1.1

Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/product/{id}/replace/{changeOptionId}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/product/{id}/replace/{changeOptionId}', params={

}, headers = headers)

print r.json()

```

`GET /product/{id}/replace/{changeOptionId}`

<h3 id="replace-operation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Subscription Suite product|
|changeOptionId|path|integer|true|The ID of a Subscription Change Option|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "zuora_id": "string",
  "name": "string",
  "description": "string",
  "feature_list": "string",
  "highlight": "string",
  "effective_start_date": "string",
  "effective_end_date": "string",
  "sku": "string",
  "updated_date": "string",
  "tenant_id": 0
}
```

<h3 id="replace-operation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Product](#schemaproduct)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## Initilization of Change Quantity Operation

<a id="opIdinitProductChangeQuantity"></a>

> Code samples

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
    req, err := http.NewRequest("GET", "/product/{id}/preview/change-quantity", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /product/{id}/preview/change-quantity HTTP/1.1

Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/product/{id}/preview/change-quantity',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/product/{id}/preview/change-quantity', params={

}, headers = headers)

print r.json()

```

`GET /product/{id}/preview/change-quantity`

<h3 id="initilization-of-change-quantity-operation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Subscription Suite product|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "zuora_id": "string",
  "name": "string",
  "description": "string",
  "feature_list": "string",
  "highlight": "string",
  "effective_start_date": "string",
  "effective_end_date": "string",
  "sku": "string",
  "updated_date": "string",
  "tenant_id": 0
}
```

<h3 id="initilization-of-change-quantity-operation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Product](#schemaproduct)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## Preview of Change Quantity Operation

<a id="opIdpreviewProductChangeQuantity"></a>

> Code samples

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
    req, err := http.NewRequest("GET", "/product/{id}/preview/change-quantity/{quantity}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /product/{id}/preview/change-quantity/{quantity} HTTP/1.1

Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/product/{id}/preview/change-quantity/{quantity}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/product/{id}/preview/change-quantity/{quantity}', params={

}, headers = headers)

print r.json()

```

`GET /product/{id}/preview/change-quantity/{quantity}`

<h3 id="preview-of-change-quantity-operation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Subscription Suite product|
|quantity|path|integer|true|Product Quantity|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "zuora_id": "string",
  "name": "string",
  "description": "string",
  "feature_list": "string",
  "highlight": "string",
  "effective_start_date": "string",
  "effective_end_date": "string",
  "sku": "string",
  "updated_date": "string",
  "tenant_id": 0
}
```

<h3 id="preview-of-change-quantity-operation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Product](#schemaproduct)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

## Change Quantity Operation

<a id="opIdProductChangeQuantity"></a>

> Code samples

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
    req, err := http.NewRequest("PUT", "/product/{id}/quantity/{quantity}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
PUT /product/{id}/quantity/{quantity} HTTP/1.1

Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.put '/product/{id}/quantity/{quantity}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.put('/product/{id}/quantity/{quantity}', params={

}, headers = headers)

print r.json()

```

`PUT /product/{id}/quantity/{quantity}`

<h3 id="change-quantity-operation-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Subscription Suite product|
|quantity|path|integer|true|Product Quantity|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "zuora_id": "string",
  "name": "string",
  "description": "string",
  "feature_list": "string",
  "highlight": "string",
  "effective_start_date": "string",
  "effective_end_date": "string",
  "sku": "string",
  "updated_date": "string",
  "tenant_id": 0
}
```

<h3 id="change-quantity-operation-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Product](#schemaproduct)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="subscription-suite-api-shop">shop</h1>

Query shop pages with multiple product selection steps

## Fetches all relevant information to display a shop page

<a id="opIdgetShopPageById"></a>

> Code samples

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

```http
GET /page/{id} HTTP/1.1

Accept: application/json

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

`GET /page/{id}`

<h3 id="fetches-all-relevant-information-to-display-a-shop-page-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
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

<h3 id="fetches-all-relevant-information-to-display-a-shop-page-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<h3 id="fetches-all-relevant-information-to-display-a-shop-page-responseschema">Response Schema</h3>

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

<h1 id="subscription-suite-api-subscription">subscription</h1>

Preview, create, and modify subscriptions

## Create new subscriptions for a user

<a id="opIdcreateSubscriptions"></a>

> Code samples

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

```http
POST /subscription HTTP/1.1

Content-Type: application/json
Accept: application/json

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

`POST /subscription`

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

<h3 id="create-new-subscriptions-for-a-user-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
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

<h3 id="create-new-subscriptions-for-a-user-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|401|[Unauthorized](https://tools.ietf.org/html/rfc7235#section-3.1)|Not authorized|None|

<h3 id="create-new-subscriptions-for-a-user-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» success|boolean|false|none|none|
|» ids|[string]|false|none|none|

<aside class="warning">
To perform this operation, you must be authenticated by means of one of the following methods:
jwtAuth, cookieAuth
</aside>

## Calculate prices for selected rate plans, quantities, and discounts

<a id="opIdpreviewSubscription"></a>

> Code samples

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

```http
POST /subscription/preview HTTP/1.1

Content-Type: application/json
Accept: application/json

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

`POST /subscription/preview`

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

<h3 id="calculate-prices-for-selected-rate-plans,-quantities,-and-discounts-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
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

<h3 id="calculate-prices-for-selected-rate-plans,-quantities,-and-discounts-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|

<h3 id="calculate-prices-for-selected-rate-plans,-quantities,-and-discounts-responseschema">Response Schema</h3>

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

<h1 id="subscription-suite-api-translation">translation</h1>

Fetch static and dynamic translations for UI elements and the product catalog

## Get static translations for a certain language

<a id="opIdgetTranslations"></a>

> Code samples

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

```http
GET /translation?lang=string HTTP/1.1

Accept: application/json

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

`GET /translation`

<h3 id="get-static-translations-for-a-certain-language-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
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

<h3 id="get-static-translations-for-a-certain-language-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="get-static-translations-for-a-certain-language-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» key|string|false|none|none|
|» translation|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Get dynamic translations for the keys specified in the request body

<a id="opIdgetDynamicTranslations"></a>

> Code samples

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

```http
POST /translation/dynamic?lang=string HTTP/1.1

Content-Type: application/json
Accept: application/json

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

`POST /translation/dynamic`

> Body parameter

```json
[
  "string"
]
```

<h3 id="get-dynamic-translations-for-the-keys-specified-in-the-request-body-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
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

<h3 id="get-dynamic-translations-for-the-keys-specified-in-the-request-body-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|

<h3 id="get-dynamic-translations-for-the-keys-specified-in-the-request-body-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» key|string|false|none|none|
|» translation|string|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="subscription-suite-api-voucher">voucher</h1>

Consume voucher codes and provide discounts

## Initialize a voucher code and block it for a certain user in case of a single use code

<a id="opIdinitVoucherCode"></a>

> Code samples

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

```http
POST /voucher-code/{code}/init HTTP/1.1

Content-Type: application/json
Accept: application/json

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

`POST /voucher-code/{code}/init`

> Body parameter

```json
{
  "pageId": "string",
  "userId": 0
}
```

<h3 id="initialize-a-voucher-code-and-block-it-for-a-certain-user-in-case-of-a-single-use-code-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
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

<h3 id="initialize-a-voucher-code-and-block-it-for-a-certain-user-in-case-of-a-single-use-code-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|

<h3 id="initialize-a-voucher-code-and-block-it-for-a-certain-user-in-case-of-a-single-use-code-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» discountRatePlanId|integer|false|none|none|
|» success|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

## Confirm and consume a voucher code

<a id="opIdconsumeVoucherCode"></a>

> Code samples

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

```http
POST /voucher-code/{code}/consume HTTP/1.1

Content-Type: application/json
Accept: application/json

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

`POST /voucher-code/{code}/consume`

> Body parameter

```json
{
  "pageId": "string",
  "userId": 0
}
```

<h3 id="confirm-and-consume-a-voucher-code-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
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

<h3 id="confirm-and-consume-a-voucher-code-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|Inline|
|400|[Bad Request](https://tools.ietf.org/html/rfc7231#section-6.5.1)|Bad request|None|

<h3 id="confirm-and-consume-a-voucher-code-responseschema">Response Schema</h3>

Status Code **200**

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|» discountRatePlanId|integer|false|none|none|
|» success|boolean|false|none|none|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="subscription-suite-api-suite-product">suite-product</h1>

## Get a suite product by id

<a id="opIdgetSuiteProductById"></a>

> Code samples

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
    req, err := http.NewRequest("GET", "/suite-product/{id}", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /suite-product/{id} HTTP/1.1

Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/suite-product/{id}',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/suite-product/{id}', params={

}, headers = headers)

print r.json()

```

`GET /suite-product/{id}`

<h3 id="get-a-suite-product-by-id-parameters">Parameters</h3>

|Name|In|Type|Required|Description|
|---|---|---|---|---|
|id|path|integer|true|The ID of a Suite Product|

> Example responses

> 200 Response

```json
{
  "id": 0,
  "name": "string",
  "description": "string",
  "feature_list": "string",
  "effective_start_date": "string",
  "effective_end_date": "string",
  "different_quantities_allowed": 0,
  "different_quantities_allowed_for_charge": 0,
  "purchasable_by_customer": 0,
  "purchasable_by_partner": 0,
  "purchasable_by_sales": 0,
  "multiple_subscriptions_allowed": 0,
  "tenant_id": 0,
  "subscription_type": "string",
  "renewal_type": "string",
  "term": 0,
  "renewal_term": 0,
  "is_auto_renew": 0,
  "cancel_behaviour": 0,
  "quantity_upgrade_behaviour": 0,
  "quantity_downgrade_behaviour": 0,
  "upgrade_behaviour": 0,
  "downgrade_behaviour": 0,
  "new_subscribe_mode": 0,
  "add_on_mode": 0,
  "has_contact_us_link": 0,
  "trusted_html": "string",
  "quantity_level": 0,
  "price_level": 0,
  "cancel_period": 0,
  "generated_id": "string",
  "cancel_mode": 0,
  "quantity_upgrade_mode": 0,
  "quantity_downgrade_mode": 0,
  "upgrade_mode": 0,
  "downgrade_mode": 0,
  "categories": [],
  "add_ons": [],
  "change_options": [],
  "subscription": {
    "id": "string",
    "account_id": "string",
    "account_number": "string",
    "account_name": "string",
    "invoice_owner_account_id": "string",
    "invoice_owner_account_number": "string",
    "invoice_owner_account_name": "string",
    "subscription_number": "string",
    "term_type": "string",
    "invoice_separately": true,
    "contract_effective_date": "string",
    "service_activation_date": "string",
    "customer_acceptance_date": "string",
    "subscription_start_date": "string",
    "term_start_date": "string",
    "term_end_date": "string",
    "initial_term": 0,
    "initial_term_period_type": "string",
    "current_term": 0,
    "current_term_period_type": "string",
    "auto_renew": true,
    "renewal_setting": "string",
    "renewal_term": 0,
    "renewal_term_period_type": "string",
    "contracted_mrr": 0,
    "total_contracted_value": 0,
    "status": "string",
    "rate_plans": [
      {
        "id": "string",
        "product_id": "string",
        "product_name": "string",
        "product_sku": "string",
        "product_rate_plan_id": "string",
        "rate_plan_name": "string",
        "suite_product_id": "string",
        "suite_product_uuid": "string",
        "rate_plan_charges": [
          {
            "id": "string",
            "original_charge_id": "string",
            "product_rate_plan_charge_id": "string",
            "number": "string",
            "name": "string",
            "type": "string",
            "model": "string",
            "version": 0,
            "pricing_summary": "string",
            "price_change_option": "string",
            "price_increase_percentage": 0,
            "currency": "string",
            "price": 0,
            "discount_apply_details": [],
            "billing_day": "string",
            "list_price_base": "string",
            "billing_period": "string",
            "billing_timing": "string",
            "billing_period_alignment": "string",
            "quantity": 0,
            "segment": 0,
            "effective_start_date": "string",
            "effective_end_date": "string",
            "processed_through_date": "string",
            "charged_through_date": "string",
            "done": true,
            "trigger_event": "string",
            "end_date_condition": "string",
            "mrr": 0,
            "dmrc": 0,
            "tcv": 0,
            "dtcv": 0,
            "description": "string"
          }
        ],
        "subscription_product_features": [
          {
            "id": "string",
            "name": "string",
            "feature_code": "string",
            "description": "string"
          }
        ]
      }
    ],
    "latest_rate_plans": [
      {
        "id": "string",
        "product_id": "string",
        "product_name": "string",
        "product_sku": "string",
        "product_rate_plan_id": "string",
        "rate_plan_name": "string",
        "suite_product_id": "string",
        "suite_product_uuid": "string",
        "rate_plan_charges": [
          {
            "id": "string",
            "original_charge_id": "string",
            "product_rate_plan_charge_id": "string",
            "number": "string",
            "name": "string",
            "type": "string",
            "model": "string",
            "version": 0,
            "pricing_summary": "string",
            "price_change_option": "string",
            "price_increase_percentage": 0,
            "currency": "string",
            "price": 0,
            "discount_apply_details": [],
            "billing_day": "string",
            "list_price_base": "string",
            "billing_period": "string",
            "billing_timing": "string",
            "billing_period_alignment": "string",
            "quantity": 0,
            "segment": 0,
            "effective_start_date": "string",
            "effective_end_date": "string",
            "processed_through_date": "string",
            "charged_through_date": "string",
            "done": true,
            "trigger_event": "string",
            "end_date_condition": "string",
            "mrr": 0,
            "dmrc": 0,
            "tcv": 0,
            "dtcv": 0,
            "description": "string"
          }
        ],
        "subscription_product_features": [
          {
            "id": "string",
            "name": "string",
            "feature_code": "string",
            "description": "string"
          }
        ]
      }
    ],
    "current_end_date": "2019-04-18"
  },
  "quantity": 0,
  "rate_plans": [
    {
      "id": "string",
      "product_id": "string",
      "product_name": "string",
      "product_sku": "string",
      "product_rate_plan_id": "string",
      "rate_plan_name": "string",
      "suite_product_id": "string",
      "suite_product_uuid": "string",
      "rate_plan_charges": [
        {
          "id": "string",
          "original_charge_id": "string",
          "product_rate_plan_charge_id": "string",
          "number": "string",
          "name": "string",
          "type": "string",
          "model": "string",
          "version": 0,
          "pricing_summary": "string",
          "price_change_option": "string",
          "price_increase_percentage": 0,
          "currency": "string",
          "price": 0,
          "discount_apply_details": [],
          "billing_day": "string",
          "list_price_base": "string",
          "billing_period": "string",
          "billing_timing": "string",
          "billing_period_alignment": "string",
          "quantity": 0,
          "segment": 0,
          "effective_start_date": "string",
          "effective_end_date": "string",
          "processed_through_date": "string",
          "charged_through_date": "string",
          "done": true,
          "trigger_event": "string",
          "end_date_condition": "string",
          "mrr": 0,
          "dmrc": 0,
          "tcv": 0,
          "dtcv": 0,
          "description": "string"
        }
      ],
      "subscription_product_features": [
        {
          "id": "string",
          "name": "string",
          "feature_code": "string",
          "description": "string"
        }
      ]
    }
  ],
  "uuid": "string"
}
```

<h3 id="get-a-suite-product-by-id-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[SuiteProduct](#schemasuiteproduct)|
|404|[Not Found](https://tools.ietf.org/html/rfc7231#section-6.5.4)|Not found|None|

<aside class="success">
This operation does not require authentication
</aside>

<h1 id="subscription-suite-api-config">config</h1>

## Get Configuration for suite

<a id="opIdconfig"></a>

> Code samples

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
    req, err := http.NewRequest("GET", "/config", data)
    req.Header = headers

    client := &http.Client{}
    resp, err := client.Do(req)
    // ...
}

```

```http
GET /config HTTP/1.1

Accept: application/json

```

```ruby
require 'rest-client'
require 'json'

headers = {
  'Accept' => 'application/json'
}

result = RestClient.get '/config',
  params: {
  }, headers: headers

p JSON.parse(result)

```

```python
import requests
headers = {
  'Accept': 'application/json'
}

r = requests.get('/config', params={

}, headers = headers)

print r.json()

```

`GET /config`

> Example responses

> 200 Response

```json
{
  "languages": [
    {
      "id": 0,
      "name": "string",
      "is_active": 0,
      "is_default": 0,
      "tenant_id": 0
    }
  ],
  "currencies": [
    {
      "id": 0,
      "iso_code": "string",
      "is_active": 0,
      "is_default": 0,
      "tenant_id": 0,
      "decimal_separator": "string",
      "thousands_separator": "string"
    }
  ],
  "cart_settings": {
    "id": 0,
    "show_product_name": 0,
    "show_rate_plan_name": 0,
    "show_feature_list": 0,
    "show_description": 0,
    "show_charges": 0,
    "use_single_quantity": 0,
    "tenant_id": 0
  },
  "checkout_settings": {
    "id": 0,
    "has_guest_checkout": 0,
    "show_charges": 0,
    "show_tax": 0,
    "show_brutto": 0,
    "show_product_name": 0,
    "tenant_id": 0,
    "has_auto_invoice": 0,
    "has_auto_payment": 0
  },
  "customer_center_settings": {
    "id": 0,
    "can_cancel_subscriptions": 0,
    "can_suspend": 0,
    "tenant_id": 0,
    "can_cancel_subscriptions_at_any_time": 0
  }
}
```

<h3 id="get-configuration-for-suite-responses">Responses</h3>

|Status|Meaning|Description|Schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|Success|[Config](#schemaconfig)|

<aside class="success">
This operation does not require authentication
</aside>

# Schemas

<h2 id="tocSaccountpaymentmethod">AccountPaymentMethod</h2>

<a id="schemaaccountpaymentmethod"></a>

```json
{
  "id": "string",
  "type": "string",
  "data": {}
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|type|string|false|none|none|
|data|object|false|none|none|

<h2 id="tocSaccount">Account</h2>

<a id="schemaaccount"></a>

```json
{
  "company_name": "string",
  "currency": "string",
  "first_name": "string",
  "last_name": "string",
  "street": "string",
  "additional_info": "string",
  "zip_code": "string",
  "city": "string",
  "state": "string",
  "country": "string",
  "email": "string",
  "phone": "string",
  "vat_id": "string",
  "has_billing_address": true,
  "is_company": true,
  "billing_first_name": "string",
  "billing_last_name": "string",
  "billing_street": "string",
  "billing_additional_info": "string",
  "billing_zip_code": "string",
  "billing_city": "string",
  "billing_country": "string",
  "billing_email": "string",
  "billing_phone": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|company_name|string|true|none|none|
|currency|string|false|none|none|
|first_name|string|true|none|none|
|last_name|string|true|none|none|
|street|string|true|none|none|
|additional_info|string|true|none|none|
|zip_code|string|true|none|none|
|city|string|true|none|none|
|state|string|false|none|none|
|country|string|true|none|none|
|email|string|true|none|none|
|phone|string|true|none|none|
|vat_id|string|true|none|none|
|has_billing_address|boolean|true|none|none|
|is_company|boolean|true|none|none|
|billing_first_name|string|true|none|none|
|billing_last_name|string|true|none|none|
|billing_street|string|true|none|none|
|billing_additional_info|string|true|none|none|
|billing_zip_code|string|true|none|none|
|billing_city|string|true|none|none|
|billing_country|string|true|none|none|
|billing_email|string|true|none|none|
|billing_phone|string|true|none|none|

<h2 id="tocSinvoice">Invoice</h2>

<a id="schemainvoice"></a>

```json
{
  "payment_amount": 0,
  "invoice_date": "2019-04-18",
  "due_date": "2019-04-18",
  "tax_amount": 0,
  "amount": 0,
  "balance": 0,
  "amount_without_tax": 0,
  "invoice_number": "string",
  "id": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|payment_amount|number|false|none|none|
|invoice_date|string(date)|false|none|none|
|due_date|string(date)|false|none|none|
|tax_amount|number|false|none|none|
|amount|number|false|none|none|
|balance|number|false|none|none|
|amount_without_tax|number|false|none|none|
|invoice_number|string|false|none|none|
|id|string|false|none|none|

<h2 id="tocSsuiteproduct">SuiteProduct</h2>

<a id="schemasuiteproduct"></a>

```json
{
  "id": 0,
  "name": "string",
  "description": "string",
  "feature_list": "string",
  "effective_start_date": "string",
  "effective_end_date": "string",
  "different_quantities_allowed": 0,
  "different_quantities_allowed_for_charge": 0,
  "purchasable_by_customer": 0,
  "purchasable_by_partner": 0,
  "purchasable_by_sales": 0,
  "multiple_subscriptions_allowed": 0,
  "tenant_id": 0,
  "subscription_type": "string",
  "renewal_type": "string",
  "term": 0,
  "renewal_term": 0,
  "is_auto_renew": 0,
  "cancel_behaviour": 0,
  "quantity_upgrade_behaviour": 0,
  "quantity_downgrade_behaviour": 0,
  "upgrade_behaviour": 0,
  "downgrade_behaviour": 0,
  "new_subscribe_mode": 0,
  "add_on_mode": 0,
  "has_contact_us_link": 0,
  "trusted_html": "string",
  "quantity_level": 0,
  "price_level": 0,
  "cancel_period": 0,
  "generated_id": "string",
  "cancel_mode": 0,
  "quantity_upgrade_mode": 0,
  "quantity_downgrade_mode": 0,
  "upgrade_mode": 0,
  "downgrade_mode": 0,
  "categories": [],
  "add_ons": [],
  "change_options": [],
  "subscription": {
    "id": "string",
    "account_id": "string",
    "account_number": "string",
    "account_name": "string",
    "invoice_owner_account_id": "string",
    "invoice_owner_account_number": "string",
    "invoice_owner_account_name": "string",
    "subscription_number": "string",
    "term_type": "string",
    "invoice_separately": true,
    "contract_effective_date": "string",
    "service_activation_date": "string",
    "customer_acceptance_date": "string",
    "subscription_start_date": "string",
    "term_start_date": "string",
    "term_end_date": "string",
    "initial_term": 0,
    "initial_term_period_type": "string",
    "current_term": 0,
    "current_term_period_type": "string",
    "auto_renew": true,
    "renewal_setting": "string",
    "renewal_term": 0,
    "renewal_term_period_type": "string",
    "contracted_mrr": 0,
    "total_contracted_value": 0,
    "status": "string",
    "rate_plans": [
      {
        "id": "string",
        "product_id": "string",
        "product_name": "string",
        "product_sku": "string",
        "product_rate_plan_id": "string",
        "rate_plan_name": "string",
        "suite_product_id": "string",
        "suite_product_uuid": "string",
        "rate_plan_charges": [
          {
            "id": "string",
            "original_charge_id": "string",
            "product_rate_plan_charge_id": "string",
            "number": "string",
            "name": "string",
            "type": "string",
            "model": "string",
            "version": 0,
            "pricing_summary": "string",
            "price_change_option": "string",
            "price_increase_percentage": 0,
            "currency": "string",
            "price": 0,
            "discount_apply_details": [],
            "billing_day": "string",
            "list_price_base": "string",
            "billing_period": "string",
            "billing_timing": "string",
            "billing_period_alignment": "string",
            "quantity": 0,
            "segment": 0,
            "effective_start_date": "string",
            "effective_end_date": "string",
            "processed_through_date": "string",
            "charged_through_date": "string",
            "done": true,
            "trigger_event": "string",
            "end_date_condition": "string",
            "mrr": 0,
            "dmrc": 0,
            "tcv": 0,
            "dtcv": 0,
            "description": "string"
          }
        ],
        "subscription_product_features": [
          {
            "id": "string",
            "name": "string",
            "feature_code": "string",
            "description": "string"
          }
        ]
      }
    ],
    "latest_rate_plans": [
      {
        "id": "string",
        "product_id": "string",
        "product_name": "string",
        "product_sku": "string",
        "product_rate_plan_id": "string",
        "rate_plan_name": "string",
        "suite_product_id": "string",
        "suite_product_uuid": "string",
        "rate_plan_charges": [
          {
            "id": "string",
            "original_charge_id": "string",
            "product_rate_plan_charge_id": "string",
            "number": "string",
            "name": "string",
            "type": "string",
            "model": "string",
            "version": 0,
            "pricing_summary": "string",
            "price_change_option": "string",
            "price_increase_percentage": 0,
            "currency": "string",
            "price": 0,
            "discount_apply_details": [],
            "billing_day": "string",
            "list_price_base": "string",
            "billing_period": "string",
            "billing_timing": "string",
            "billing_period_alignment": "string",
            "quantity": 0,
            "segment": 0,
            "effective_start_date": "string",
            "effective_end_date": "string",
            "processed_through_date": "string",
            "charged_through_date": "string",
            "done": true,
            "trigger_event": "string",
            "end_date_condition": "string",
            "mrr": 0,
            "dmrc": 0,
            "tcv": 0,
            "dtcv": 0,
            "description": "string"
          }
        ],
        "subscription_product_features": [
          {
            "id": "string",
            "name": "string",
            "feature_code": "string",
            "description": "string"
          }
        ]
      }
    ],
    "current_end_date": "2019-04-18"
  },
  "quantity": 0,
  "rate_plans": [
    {
      "id": "string",
      "product_id": "string",
      "product_name": "string",
      "product_sku": "string",
      "product_rate_plan_id": "string",
      "rate_plan_name": "string",
      "suite_product_id": "string",
      "suite_product_uuid": "string",
      "rate_plan_charges": [
        {
          "id": "string",
          "original_charge_id": "string",
          "product_rate_plan_charge_id": "string",
          "number": "string",
          "name": "string",
          "type": "string",
          "model": "string",
          "version": 0,
          "pricing_summary": "string",
          "price_change_option": "string",
          "price_increase_percentage": 0,
          "currency": "string",
          "price": 0,
          "discount_apply_details": [],
          "billing_day": "string",
          "list_price_base": "string",
          "billing_period": "string",
          "billing_timing": "string",
          "billing_period_alignment": "string",
          "quantity": 0,
          "segment": 0,
          "effective_start_date": "string",
          "effective_end_date": "string",
          "processed_through_date": "string",
          "charged_through_date": "string",
          "done": true,
          "trigger_event": "string",
          "end_date_condition": "string",
          "mrr": 0,
          "dmrc": 0,
          "tcv": 0,
          "dtcv": 0,
          "description": "string"
        }
      ],
      "subscription_product_features": [
        {
          "id": "string",
          "name": "string",
          "feature_code": "string",
          "description": "string"
        }
      ]
    }
  ],
  "uuid": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|true|none|none|
|name|string|true|none|none|
|description|string|true|none|none|
|feature_list|string|true|none|none|
|effective_start_date|string|true|none|none|
|effective_end_date|string|true|none|none|
|different_quantities_allowed|number|true|none|none|
|different_quantities_allowed_for_charge|number|true|none|none|
|purchasable_by_customer|number|true|none|none|
|purchasable_by_partner|number|true|none|none|
|purchasable_by_sales|number|true|none|none|
|multiple_subscriptions_allowed|number|true|none|none|
|tenant_id|number|true|none|none|
|subscription_type|string|true|none|none|
|renewal_type|string|true|none|none|
|term|number|true|none|none|
|renewal_term|number|true|none|none|
|is_auto_renew|number|true|none|none|
|cancel_behaviour|number|true|none|none|
|quantity_upgrade_behaviour|number|true|none|none|
|quantity_downgrade_behaviour|number|true|none|none|
|upgrade_behaviour|number|true|none|none|
|downgrade_behaviour|number|true|none|none|
|new_subscribe_mode|number|true|none|none|
|add_on_mode|number|true|none|none|
|has_contact_us_link|number|true|none|none|
|trusted_html|string|true|none|none|
|quantity_level|number|true|none|none|
|price_level|number|true|none|none|
|cancel_period|number|true|none|none|
|generated_id|string|true|none|none|
|cancel_mode|number|true|none|none|
|quantity_upgrade_mode|number|true|none|none|
|quantity_downgrade_mode|number|true|none|none|
|upgrade_mode|number|true|none|none|
|downgrade_mode|number|true|none|none|
|categories|array|true|none|none|
|add_ons|array|true|none|none|
|change_options|array|true|none|none|
|subscription|[Subscription](#schemasubscription)|true|none|none|
|quantity|number|true|none|none|
|rate_plans|[[AccountRatePlan](#schemaaccountrateplan)]|true|none|none|
|uuid|string|true|none|none|

<h2 id="tocSsubscription">Subscription</h2>

<a id="schemasubscription"></a>

```json
{
  "id": "string",
  "account_id": "string",
  "account_number": "string",
  "account_name": "string",
  "invoice_owner_account_id": "string",
  "invoice_owner_account_number": "string",
  "invoice_owner_account_name": "string",
  "subscription_number": "string",
  "term_type": "string",
  "invoice_separately": true,
  "contract_effective_date": "string",
  "service_activation_date": "string",
  "customer_acceptance_date": "string",
  "subscription_start_date": "string",
  "term_start_date": "string",
  "term_end_date": "string",
  "initial_term": 0,
  "initial_term_period_type": "string",
  "current_term": 0,
  "current_term_period_type": "string",
  "auto_renew": true,
  "renewal_setting": "string",
  "renewal_term": 0,
  "renewal_term_period_type": "string",
  "contracted_mrr": 0,
  "total_contracted_value": 0,
  "status": "string",
  "rate_plans": [
    {
      "id": "string",
      "product_id": "string",
      "product_name": "string",
      "product_sku": "string",
      "product_rate_plan_id": "string",
      "rate_plan_name": "string",
      "suite_product_id": "string",
      "suite_product_uuid": "string",
      "rate_plan_charges": [
        {
          "id": "string",
          "original_charge_id": "string",
          "product_rate_plan_charge_id": "string",
          "number": "string",
          "name": "string",
          "type": "string",
          "model": "string",
          "version": 0,
          "pricing_summary": "string",
          "price_change_option": "string",
          "price_increase_percentage": 0,
          "currency": "string",
          "price": 0,
          "discount_apply_details": [],
          "billing_day": "string",
          "list_price_base": "string",
          "billing_period": "string",
          "billing_timing": "string",
          "billing_period_alignment": "string",
          "quantity": 0,
          "segment": 0,
          "effective_start_date": "string",
          "effective_end_date": "string",
          "processed_through_date": "string",
          "charged_through_date": "string",
          "done": true,
          "trigger_event": "string",
          "end_date_condition": "string",
          "mrr": 0,
          "dmrc": 0,
          "tcv": 0,
          "dtcv": 0,
          "description": "string"
        }
      ],
      "subscription_product_features": [
        {
          "id": "string",
          "name": "string",
          "feature_code": "string",
          "description": "string"
        }
      ]
    }
  ],
  "latest_rate_plans": [
    {
      "id": "string",
      "product_id": "string",
      "product_name": "string",
      "product_sku": "string",
      "product_rate_plan_id": "string",
      "rate_plan_name": "string",
      "suite_product_id": "string",
      "suite_product_uuid": "string",
      "rate_plan_charges": [
        {
          "id": "string",
          "original_charge_id": "string",
          "product_rate_plan_charge_id": "string",
          "number": "string",
          "name": "string",
          "type": "string",
          "model": "string",
          "version": 0,
          "pricing_summary": "string",
          "price_change_option": "string",
          "price_increase_percentage": 0,
          "currency": "string",
          "price": 0,
          "discount_apply_details": [],
          "billing_day": "string",
          "list_price_base": "string",
          "billing_period": "string",
          "billing_timing": "string",
          "billing_period_alignment": "string",
          "quantity": 0,
          "segment": 0,
          "effective_start_date": "string",
          "effective_end_date": "string",
          "processed_through_date": "string",
          "charged_through_date": "string",
          "done": true,
          "trigger_event": "string",
          "end_date_condition": "string",
          "mrr": 0,
          "dmrc": 0,
          "tcv": 0,
          "dtcv": 0,
          "description": "string"
        }
      ],
      "subscription_product_features": [
        {
          "id": "string",
          "name": "string",
          "feature_code": "string",
          "description": "string"
        }
      ]
    }
  ],
  "current_end_date": "2019-04-18"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|true|none|none|
|account_id|string|true|none|none|
|account_number|string|true|none|none|
|account_name|string|true|none|none|
|invoice_owner_account_id|string|true|none|none|
|invoice_owner_account_number|string|true|none|none|
|invoice_owner_account_name|string|true|none|none|
|subscription_number|string|true|none|none|
|term_type|string|true|none|none|
|invoice_separately|boolean|true|none|none|
|contract_effective_date|string|true|none|none|
|service_activation_date|string|true|none|none|
|customer_acceptance_date|string|true|none|none|
|subscription_start_date|string|true|none|none|
|term_start_date|string|true|none|none|
|term_end_date|string|true|none|none|
|initial_term|number|true|none|none|
|initial_term_period_type|string|true|none|none|
|current_term|number|true|none|none|
|current_term_period_type|string|true|none|none|
|auto_renew|boolean|true|none|none|
|renewal_setting|string|true|none|none|
|renewal_term|number|true|none|none|
|renewal_term_period_type|string|true|none|none|
|contracted_mrr|number|true|none|none|
|total_contracted_value|number|true|none|none|
|status|string|true|none|none|
|rate_plans|[[AccountRatePlan](#schemaaccountrateplan)]|true|none|none|
|latest_rate_plans|[[AccountRatePlan](#schemaaccountrateplan)]|false|none|none|
|current_end_date|string(date)|true|none|none|

<h2 id="tocSaccountrateplan">AccountRatePlan</h2>

<a id="schemaaccountrateplan"></a>

```json
{
  "id": "string",
  "product_id": "string",
  "product_name": "string",
  "product_sku": "string",
  "product_rate_plan_id": "string",
  "rate_plan_name": "string",
  "suite_product_id": "string",
  "suite_product_uuid": "string",
  "rate_plan_charges": [
    {
      "id": "string",
      "original_charge_id": "string",
      "product_rate_plan_charge_id": "string",
      "number": "string",
      "name": "string",
      "type": "string",
      "model": "string",
      "version": 0,
      "pricing_summary": "string",
      "price_change_option": "string",
      "price_increase_percentage": 0,
      "currency": "string",
      "price": 0,
      "discount_apply_details": [],
      "billing_day": "string",
      "list_price_base": "string",
      "billing_period": "string",
      "billing_timing": "string",
      "billing_period_alignment": "string",
      "quantity": 0,
      "segment": 0,
      "effective_start_date": "string",
      "effective_end_date": "string",
      "processed_through_date": "string",
      "charged_through_date": "string",
      "done": true,
      "trigger_event": "string",
      "end_date_condition": "string",
      "mrr": 0,
      "dmrc": 0,
      "tcv": 0,
      "dtcv": 0,
      "description": "string"
    }
  ],
  "subscription_product_features": [
    {
      "id": "string",
      "name": "string",
      "feature_code": "string",
      "description": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|product_id|string|false|none|none|
|product_name|string|false|none|none|
|product_sku|string|false|none|none|
|product_rate_plan_id|string|false|none|none|
|rate_plan_name|string|false|none|none|
|suite_product_id|string|false|none|none|
|suite_product_uuid|string|false|none|none|
|rate_plan_charges|[[RatePlanCharge](#schemarateplancharge)]|false|none|none|
|subscription_product_features|[[SubscriptionProductFeature](#schemasubscriptionproductfeature)]|false|none|none|

<h2 id="tocSrateplancharge">RatePlanCharge</h2>

<a id="schemarateplancharge"></a>

```json
{
  "id": "string",
  "original_charge_id": "string",
  "product_rate_plan_charge_id": "string",
  "number": "string",
  "name": "string",
  "type": "string",
  "model": "string",
  "version": 0,
  "pricing_summary": "string",
  "price_change_option": "string",
  "price_increase_percentage": 0,
  "currency": "string",
  "price": 0,
  "discount_apply_details": [],
  "billing_day": "string",
  "list_price_base": "string",
  "billing_period": "string",
  "billing_timing": "string",
  "billing_period_alignment": "string",
  "quantity": 0,
  "segment": 0,
  "effective_start_date": "string",
  "effective_end_date": "string",
  "processed_through_date": "string",
  "charged_through_date": "string",
  "done": true,
  "trigger_event": "string",
  "end_date_condition": "string",
  "mrr": 0,
  "dmrc": 0,
  "tcv": 0,
  "dtcv": 0,
  "description": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|original_charge_id|string|false|none|none|
|product_rate_plan_charge_id|string|false|none|none|
|number|string|false|none|none|
|name|string|false|none|none|
|type|string|false|none|none|
|model|string|false|none|none|
|version|number|false|none|none|
|pricing_summary|string|false|none|none|
|price_change_option|string|false|none|none|
|price_increase_percentage|number|false|none|none|
|currency|string|false|none|none|
|price|number|false|none|none|
|discount_apply_details|array|false|none|none|
|billing_day|string|false|none|none|
|list_price_base|string|false|none|none|
|billing_period|string|false|none|none|
|billing_timing|string|false|none|none|
|billing_period_alignment|string|false|none|none|
|quantity|number|false|none|none|
|segment|number|false|none|none|
|effective_start_date|string|false|none|none|
|effective_end_date|string|false|none|none|
|processed_through_date|string|false|none|none|
|charged_through_date|string|false|none|none|
|done|boolean|false|none|none|
|trigger_event|string|false|none|none|
|end_date_condition|string|false|none|none|
|mrr|number|false|none|none|
|dmrc|number|false|none|none|
|tcv|number|false|none|none|
|dtcv|number|false|none|none|
|description|string|false|none|none|

<h2 id="tocSsubscriptionproductfeature">SubscriptionProductFeature</h2>

<a id="schemasubscriptionproductfeature"></a>

```json
{
  "id": "string",
  "name": "string",
  "feature_code": "string",
  "description": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|string|false|none|none|
|name|string|false|none|none|
|feature_code|string|false|none|none|
|description|string|false|none|none|

<h2 id="tocSsubscriptionandrateplan">SubscriptionAndRatePlan</h2>

<a id="schemasubscriptionandrateplan"></a>

```json
{
  "subscription": {
    "id": "string",
    "account_id": "string",
    "account_number": "string",
    "account_name": "string",
    "invoice_owner_account_id": "string",
    "invoice_owner_account_number": "string",
    "invoice_owner_account_name": "string",
    "subscription_number": "string",
    "term_type": "string",
    "invoice_separately": true,
    "contract_effective_date": "string",
    "service_activation_date": "string",
    "customer_acceptance_date": "string",
    "subscription_start_date": "string",
    "term_start_date": "string",
    "term_end_date": "string",
    "initial_term": 0,
    "initial_term_period_type": "string",
    "current_term": 0,
    "current_term_period_type": "string",
    "auto_renew": true,
    "renewal_setting": "string",
    "renewal_term": 0,
    "renewal_term_period_type": "string",
    "contracted_mrr": 0,
    "total_contracted_value": 0,
    "status": "string",
    "rate_plans": [
      {
        "id": "string",
        "product_id": "string",
        "product_name": "string",
        "product_sku": "string",
        "product_rate_plan_id": "string",
        "rate_plan_name": "string",
        "suite_product_id": "string",
        "suite_product_uuid": "string",
        "rate_plan_charges": [
          {
            "id": "string",
            "original_charge_id": "string",
            "product_rate_plan_charge_id": "string",
            "number": "string",
            "name": "string",
            "type": "string",
            "model": "string",
            "version": 0,
            "pricing_summary": "string",
            "price_change_option": "string",
            "price_increase_percentage": 0,
            "currency": "string",
            "price": 0,
            "discount_apply_details": [],
            "billing_day": "string",
            "list_price_base": "string",
            "billing_period": "string",
            "billing_timing": "string",
            "billing_period_alignment": "string",
            "quantity": 0,
            "segment": 0,
            "effective_start_date": "string",
            "effective_end_date": "string",
            "processed_through_date": "string",
            "charged_through_date": "string",
            "done": true,
            "trigger_event": "string",
            "end_date_condition": "string",
            "mrr": 0,
            "dmrc": 0,
            "tcv": 0,
            "dtcv": 0,
            "description": "string"
          }
        ],
        "subscription_product_features": [
          {
            "id": "string",
            "name": "string",
            "feature_code": "string",
            "description": "string"
          }
        ]
      }
    ],
    "latest_rate_plans": [
      {
        "id": "string",
        "product_id": "string",
        "product_name": "string",
        "product_sku": "string",
        "product_rate_plan_id": "string",
        "rate_plan_name": "string",
        "suite_product_id": "string",
        "suite_product_uuid": "string",
        "rate_plan_charges": [
          {
            "id": "string",
            "original_charge_id": "string",
            "product_rate_plan_charge_id": "string",
            "number": "string",
            "name": "string",
            "type": "string",
            "model": "string",
            "version": 0,
            "pricing_summary": "string",
            "price_change_option": "string",
            "price_increase_percentage": 0,
            "currency": "string",
            "price": 0,
            "discount_apply_details": [],
            "billing_day": "string",
            "list_price_base": "string",
            "billing_period": "string",
            "billing_timing": "string",
            "billing_period_alignment": "string",
            "quantity": 0,
            "segment": 0,
            "effective_start_date": "string",
            "effective_end_date": "string",
            "processed_through_date": "string",
            "charged_through_date": "string",
            "done": true,
            "trigger_event": "string",
            "end_date_condition": "string",
            "mrr": 0,
            "dmrc": 0,
            "tcv": 0,
            "dtcv": 0,
            "description": "string"
          }
        ],
        "subscription_product_features": [
          {
            "id": "string",
            "name": "string",
            "feature_code": "string",
            "description": "string"
          }
        ]
      }
    ],
    "current_end_date": "2019-04-18"
  },
  "id": "string",
  "product_id": "string",
  "product_name": "string",
  "product_sku": "string",
  "product_rate_plan_id": "string",
  "rate_plan_name": "string",
  "suite_product_id": "string",
  "suite_product_uuid": "string",
  "rate_plan_charges": [
    {
      "id": "string",
      "original_charge_id": "string",
      "product_rate_plan_charge_id": "string",
      "number": "string",
      "name": "string",
      "type": "string",
      "model": "string",
      "version": 0,
      "pricing_summary": "string",
      "price_change_option": "string",
      "price_increase_percentage": 0,
      "currency": "string",
      "price": 0,
      "discount_apply_details": [],
      "billing_day": "string",
      "list_price_base": "string",
      "billing_period": "string",
      "billing_timing": "string",
      "billing_period_alignment": "string",
      "quantity": 0,
      "segment": 0,
      "effective_start_date": "string",
      "effective_end_date": "string",
      "processed_through_date": "string",
      "charged_through_date": "string",
      "done": true,
      "trigger_event": "string",
      "end_date_condition": "string",
      "mrr": 0,
      "dmrc": 0,
      "tcv": 0,
      "dtcv": 0,
      "description": "string"
    }
  ],
  "subscription_product_features": [
    {
      "id": "string",
      "name": "string",
      "feature_code": "string",
      "description": "string"
    }
  ]
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|subscription|[Subscription](#schemasubscription)|false|none|none|
|id|string|false|none|none|
|product_id|string|false|none|none|
|product_name|string|false|none|none|
|product_sku|string|false|none|none|
|product_rate_plan_id|string|false|none|none|
|rate_plan_name|string|false|none|none|
|suite_product_id|string|false|none|none|
|suite_product_uuid|string|false|none|none|
|rate_plan_charges|[[RatePlanCharge](#schemarateplancharge)]|false|none|none|
|subscription_product_features|[[SubscriptionProductFeature](#schemasubscriptionproductfeature)]|false|none|none|

<h2 id="tocSconfig">Config</h2>

<a id="schemaconfig"></a>

```json
{
  "languages": [
    {
      "id": 0,
      "name": "string",
      "is_active": 0,
      "is_default": 0,
      "tenant_id": 0
    }
  ],
  "currencies": [
    {
      "id": 0,
      "iso_code": "string",
      "is_active": 0,
      "is_default": 0,
      "tenant_id": 0,
      "decimal_separator": "string",
      "thousands_separator": "string"
    }
  ],
  "cart_settings": {
    "id": 0,
    "show_product_name": 0,
    "show_rate_plan_name": 0,
    "show_feature_list": 0,
    "show_description": 0,
    "show_charges": 0,
    "use_single_quantity": 0,
    "tenant_id": 0
  },
  "checkout_settings": {
    "id": 0,
    "has_guest_checkout": 0,
    "show_charges": 0,
    "show_tax": 0,
    "show_brutto": 0,
    "show_product_name": 0,
    "tenant_id": 0,
    "has_auto_invoice": 0,
    "has_auto_payment": 0
  },
  "customer_center_settings": {
    "id": 0,
    "can_cancel_subscriptions": 0,
    "can_suspend": 0,
    "tenant_id": 0,
    "can_cancel_subscriptions_at_any_time": 0
  }
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|languages|[[Language](#schemalanguage)]|false|none|none|
|currencies|[[Currency](#schemacurrency)]|false|none|none|
|cart_settings|[CartSettings](#schemacartsettings)|false|none|none|
|checkout_settings|[CheckoutSettings](#schemacheckoutsettings)|false|none|none|
|customer_center_settings|[CustomerCenterSettings](#schemacustomercentersettings)|false|none|none|

<h2 id="tocSlanguage">Language</h2>

<a id="schemalanguage"></a>

```json
{
  "id": 0,
  "name": "string",
  "is_active": 0,
  "is_default": 0,
  "tenant_id": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|none|
|name|string|false|none|none|
|is_active|number|false|none|none|
|is_default|number|false|none|none|
|tenant_id|number|false|none|none|

<h2 id="tocScurrency">Currency</h2>

<a id="schemacurrency"></a>

```json
{
  "id": 0,
  "iso_code": "string",
  "is_active": 0,
  "is_default": 0,
  "tenant_id": 0,
  "decimal_separator": "string",
  "thousands_separator": "string"
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|none|
|iso_code|string|false|none|none|
|is_active|number|false|none|none|
|is_default|number|false|none|none|
|tenant_id|number|false|none|none|
|decimal_separator|string|false|none|none|
|thousands_separator|string|false|none|none|

<h2 id="tocScartsettings">CartSettings</h2>

<a id="schemacartsettings"></a>

```json
{
  "id": 0,
  "show_product_name": 0,
  "show_rate_plan_name": 0,
  "show_feature_list": 0,
  "show_description": 0,
  "show_charges": 0,
  "use_single_quantity": 0,
  "tenant_id": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|none|
|show_product_name|number|false|none|none|
|show_rate_plan_name|number|false|none|none|
|show_feature_list|number|false|none|none|
|show_description|number|false|none|none|
|show_charges|number|false|none|none|
|use_single_quantity|number|false|none|none|
|tenant_id|number|false|none|none|

<h2 id="tocScheckoutsettings">CheckoutSettings</h2>

<a id="schemacheckoutsettings"></a>

```json
{
  "id": 0,
  "has_guest_checkout": 0,
  "show_charges": 0,
  "show_tax": 0,
  "show_brutto": 0,
  "show_product_name": 0,
  "tenant_id": 0,
  "has_auto_invoice": 0,
  "has_auto_payment": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|none|
|has_guest_checkout|number|false|none|none|
|show_charges|number|false|none|none|
|show_tax|number|false|none|none|
|show_brutto|number|false|none|none|
|show_product_name|number|false|none|none|
|tenant_id|number|false|none|none|
|has_auto_invoice|number|false|none|none|
|has_auto_payment|number|false|none|none|

<h2 id="tocScustomercentersettings">CustomerCenterSettings</h2>

<a id="schemacustomercentersettings"></a>

```json
{
  "id": 0,
  "can_cancel_subscriptions": 0,
  "can_suspend": 0,
  "tenant_id": 0,
  "can_cancel_subscriptions_at_any_time": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|none|
|can_cancel_subscriptions|number|false|none|none|
|can_suspend|number|false|none|none|
|tenant_id|number|false|none|none|
|can_cancel_subscriptions_at_any_time|number|false|none|none|

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
  "id": 0,
  "zuora_id": "string",
  "name": "string",
  "description": "string",
  "feature_list": "string",
  "highlight": "string",
  "effective_start_date": "string",
  "effective_end_date": "string",
  "sku": "string",
  "updated_date": "string",
  "tenant_id": 0
}

```

### Properties

|Name|Type|Required|Restrictions|Description|
|---|---|---|---|---|
|id|number|false|none|none|
|zuora_id|string|false|none|none|
|name|string|false|none|none|
|description|string|false|none|none|
|feature_list|string|false|none|none|
|highlight|string|false|none|none|
|effective_start_date|string|false|none|none|
|effective_end_date|string|false|none|none|
|sku|string|false|none|none|
|updated_date|string|false|none|none|
|tenant_id|number|false|none|none|

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

