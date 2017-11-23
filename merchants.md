# Merchants

## Merchants Registration

This document describes how to register merchants on Pick through API.
If youre account is a **marketplace** you need to create a merchant for each of your seller in your account.
Please make sure you have an API-key to successfully create a merchant. If you still dont have an API-key for your account, you
can email us at support@pick.sa.

### API Access Points

<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /merchants/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> POST </td>
  </tr>
  <tr>
    <td valign="top"><strong>Parameters</strong></td>
    <td>
      <ul>
        <li><code>first_name</code> [String]
        <li><code>last_name</code> [String]
        <li><code>phone</code> [String]
        <li><code>url</code> [String]
        <li><code>store_name</code> [String]
        <li><code>location</code> [String] This should be a coordinate separated with comma(,) example: <code>"24.7,46.6"</code>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
      <ul>
        <li><code>id</code> [Number/Integer]
        <li><code>first_name</code> [String]
        <li><code>last_name</code> [String]
        <li><code>phone</code> [String]
        <li><code>url</code> [String]
        <li><code>store_name</code> [String]
        <li><code>location</code> [String]
        <li><code>owner</code> [String]
        <li><code>date_created</code> [String]
      </ul>
    </td>
  </tr>
</table>


### Example

For testing purposes, use `https://sandbox.pick.sa/` to create a merchant.


#### Request

```
POST /merchants/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: <your-api-key>

Payload:
{
  "first_name": "John",
  "last_name": "Doe",
  "phone": "0987654321",
  "url": "http://my-store.com/test-store/",
  "store_name": "Test Store",
  "location": "24.7,46.6"
}

```

#### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

{
  "id": 111,
  "first_name": "John",
  "last_name": "Doe",
  "store_name": "Test Store",
  "location": "24.7,46.6",
  "url": "http://my-store.com/test-store/",
  "phone": "0987654321",
  "owner": "owner@admin.com",
  "date_created": "2017-11-09T11:09:59.585708"
}
```

## Retrieving Merchants

This document describes how to retrieve merchants on Pick through API.
Please make sure you have an API-key to successfully create a merchant. If you still dont have an API-key for your account, you
can email us at support@pick.sa.

### API Access Points

<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /merchants/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
    List of merchants with the following details:
      <ul>
        <li><code>id</code> [Number/Integer]
        <li><code>first_name</code> [String]
        <li><code>last_name</code> [String]
        <li><code>phone</code> [String]
        <li><code>url</code> [String]
        <li><code>store_name</code> [String]
        <li><code>location</code> [String]
        <li><code>owner</code> [String]
        <li><code>date_created</code> [String]
      </ul>
    </td>
  </tr>
</table>

### Example

For testing purposes, use `https://sandbox.pick.sa/` to retrieve merchants.


#### Request

```
GET /merchants/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: <your-api-key>

```

#### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

[
  {
    "id": 111,
    "first_name": "John",
    "last_name": "Doe",
    "store_name": "Test Store",
    "location": "24.7,46.6",
    "url": "http://my-store.com/test-store/",
    "phone": "0987654321",
    "owner": "owner@admin.com",
    "date_created": "2017-11-09T11:09:59.585708"
  },
]
```
