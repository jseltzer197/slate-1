---
title: API Reference

language_tabs:
  - cUrl
  - shell
  - ruby
  - python

toc_footers:
  - <a href='#'>Your Mom.  Sign Up for a Developer Key</a>
  - <a href='http://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

The eBay Enterprise Commerce Technologies Public APIs are our retail interfaces that are used to access the resources and functionality of the eBay Enterprise Commerce Platform and Integrated Business User Tools.

The Consumer Interaction API provides access to the following resources:

* Categories
* Products
* Promotions
* Carts (Checkout)
* Orders
* Tokens
* Accounts

The Consumer Interaction API uses HTTP verbs and a RESTful endpoint structure. Access tokens are used for consumer-level authentication and authorization. Request and response payloads are optimized for JSON format.
This document describes the API endpoints and request/response payloads that can be used to integrate external consumer interaction applications with the Commerce Platform.

We have language bindings in cUrl, Shell, Ruby, and Python. You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

<aside class="notice">
You must replace `meowmeowmeow` with your personal API key.
</aside>

# REST Convention
All service integrations are accomplished via REST calls from client applications to the Consumer Interaction API. Acknowledgements and error handling are supported and documented within each of the underlying service specifications.
The design of the Consumer Interaction API provides:

* Access to e-commerce functions in a simple, easy to understand interface.
* Secure calls with no sensitive or secret information exposed in HTTP access logs.
* Industry standard URI structures to enable detailed analytics capability for eBay Enterprise and client reporting.

In order to achieve these capabilities, the eBay Enterprise Consumer Interaction specification employs a RESTful URI structure, using standard HTTP methods (GET, PUT, POST, DELETE). This provides for consistent, standards-based interactions with client applications while maintaining the needed security and functionality that enterprise customers demand.











# Authentication

> To authorize, use this code:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: meowmeowmeow"
```

> Make sure to replace `meowmeowmeow` with your API key.

Kittn uses API keys to allow access to the API. You can register a new Kittn API key at our [developer portal](http://example.com/developers).

Kittn expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: meowmeowmeow`

<aside class="notice">
You must replace `meowmeowmeow` with your personal API key.
</aside>

# Kittens

## Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Isis",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/3"
  -H "Authorization: meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Isis",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">If you're not using an administrator API key, note that some kittens will return 403 Forbidden if they are hidden for admins only.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the cat to retrieve

