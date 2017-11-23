# Merchants
For testing purposes, please use `https://sandbox.pick.sa/` to create, retrieve and delete merchants.<br>
For example: `https://sandbox.pick.sa/merchants/`
<br><br>
This document explains on how to create, retrieve and delete merchants in your account.
If youre account is a **marketplace** you need to create a merchant for each of your seller in your account.
<br>
## Creating Merchants

This section describes how to register merchants on Pick through API.
Please make sure you have an API key to successfully create a merchant. If you haven't receive your API key for your account through email, you can email us at support@pick.sa.

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


#### Example

###### Request

```
POST /merchants/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: {your-api-key}

Payload:
  {
    "first_name": "Anna",
    "last_name": "Cruz",
    "store_name": "My Dress Store",
    "location": "24.6,46.5",
    "url": "http://my-store.com/my-dress-store/",
    "phone": "0987654322"
  }

```

###### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

  {
    "id": 2,
    "first_name": "Anna",
    "last_name": "Cruz",
    "store_name": "My Dress Store",
    "location": "24.6,46.5",
    "url": "http://my-store.com/my-dress-store/",
    "phone": "0987654322",
    "owner": "patrick@pick.sa",
    "date_created": "2017-11-23T08:35:16.430303Z"
  }
```

## Retrieving Merchants

This section describes how to retrieve merchants on Pick through API.
Please make sure you have an API key to successfully create a merchant. If you haven't receive your API key for your account through email, you can email us at support@pick.sa.

### API Access Points
#### Retrieve a merchant details
You can get merchant details using this API Access Point.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /merchants/{merchant-id}/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
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

#### Example


##### Request

```
GET /merchants/2/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: {your-api-key}

```

##### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

  {
    "id": 2,
    "first_name": "Anna",
    "last_name": "Cruz",
    "store_name": "My Dress Store",
    "location": "24.6,46.5",
    "url": "http://my-store.com/my-dress-store/",
    "phone": "0987654322",
    "owner": "patrick@pick.sa",
    "date_created": "2017-11-23T08:35:16.430303Z"
  }

```

#### Retrieve ALL Merchant details
You can get all your merchants using this API Access Point.
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

#### Example


##### Request

```
GET /merchants/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: {your-api-key}

```

##### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

[
  {
    "id": 2,
    "first_name": "Anna",
    "last_name": "Cruz",
    "store_name": "My Dress Store",
    "location": "24.6,46.5",
    "url": "http://my-store.com/my-dress-store/",
    "phone": "0987654322",
    "owner": "patrick@pick.sa",
    "date_created": "2017-11-23T08:35:16.430303Z"
  },
  {
    "id": 1,
    "first_name": "John",
    "last_name": "Doe",
    "store_name": "Test Store",
    "location": "24.7,46.6",
    "url": "http://my-store.com/test-store/",
    "phone": "0987654321",
    "owner": "patrick@pick.sa",
    "date_created": "2017-11-23T08:35:09.144652Z"
  }
]
```

## Deleting Merchants

This section describes how to delete a merchant on Pick through API.
Please make sure you have an API key to successfully delete a merchant. If you haven't receive your API key for your account through email, you can email us at support@pick.sa.

### API Access Points
You can delete a merchant using this API Access Point.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /merchants/{merchant-id}/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> DELETE </td>
  </tr>
</table>


#### Example

##### Request

```
POST /merchants/2/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: {your-api-key}
```

##### Success Response

```
HTTP/1.0 204 OK 
```
