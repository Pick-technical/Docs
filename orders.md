# Orders
For testing purposes, please use `https://sandbox.pick.sa/` to create, retrieve and cancel orders.<br>
For example: `https://sandbox.pick.sa/orders/`
<br><br>
This document explains on how to create, retrieve and cancel orders in your account.
<br><br>
For more information about the parameters and response in creating orders, click <a href="https://github.com/Pick-technical/Docs/blob/master/order_parameters_and_response_description.md">here</a>.
## Creating Orders with a Marketplace Account

This section describes how to create orders if your account is a **marketplace** on Pick through API.
Please make sure you have an API key to successfully create orders. If you haven't receive your API key for your account through email, you can email us at support@pick.sa.

### API Access Points

<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /merchants/{merchant-id}/orders/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> POST </td>
  </tr>
  <tr>
    <td valign="top"><strong>Parameters</strong></td>
    <td>
      <ul>
        <li><code>items</code> [String]</li>
        <li><code>payment_type</code> [String]</li>
        <li><code>pickup_location</code> [String]</li>
        <li><code>pickup_time</code> [String]</li>
        <li><code>receiver_name</code> [String]</li>
        <li><code>receiver_phone</code> [String] </li>
        <li><code>service_type</code> [String] </li>
        <li><code>price</code> [Number/Integer/Float] </li>
        <li><code>delivery_notes</code> [String] OPTIONAL</li>
        <li><code>dropoff_location</code> [String] OPTIONAL</li>
        <li><code>dropoff_time</code> [String] OPTIONAL</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
      <ul>
        <li><code>id</code> [Number/Integer]</li>
        <li><code>created_at</code> [String]</li>
        <li><code>owner</code> [String]</li>
        <li><code>service_type</code> [String]</li>
        <li><code>pickup_location</code> [String]</li>
        <li><code>dropoff_location</code> [String]</li>
        <li><code>receiver_name</code> [String]</li>
        <li><code>eceiver_phone</code> [String]</li>
        <li><code>pickup_time</code> [String]</li>     
        <li><code>dropoff_time</code> [Number/Integer]</li>
        <li><code>items</code> [Number/Integer]</li>
        <li><code>payment_type</code> [Number/Integer]</li>
        <li><code>cod_fees</code> [Number/Integer]</li>
        <li><code>status</code> [Number/Integer]</li>
        <li><code>status_code</code> [Number/Integer]</li>
        <li><code>delivery_notes</code> [Number/Integer]</li>
        <li><code>price</code> [Number/Integer]</li>
        <li><code>less_fees</code> [Number/Integer]</li>
        <li><code>packaging</code> [Number/Integer]</li>
        <li><code>container</code> [Number/Integer]</li>
        <li><code>insurance</code> [Number/Integer]</li>
        <li><code>additional_services</code> [Number/Integer]</li>
        <li><code>service_cost</code> [Number/Integer]</li>
        <li><code>width</code> [Number/Integer]</li>
        <li><code>length</code> [Number/Integer]</li>
        <li><code>weight</code> [Number/Integer]</li>
        <li><code>height</code> [Number/Integer]</li>
        <li><code>tracking_no</code> [Number/Integer]</li>
        <li><code>phone</code> [Number/Integer]</li>
        <li><code>full_name</code> [Number/Integer]</li>
        <li><code>store_name</code> [Number/Integer]</li>
        <li><code>pickup_address</code> [Number/Integer]</li>
        <li><code>dropoff_address</code> [Number/Integer]</li>      
      </ul>
    </td>
  </tr>
</table>


#### Example

###### Request

```
POST /merchants/35/orders/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: {your-api-key}

Payload:
  {
    "items": "food",
    "payment_type": "COD",
    "pickup_location": "24.7,46.6",
    "pickup_time": "2018-10-04 12:50 AM",
    "receiver_name": "John Doe",
    "receiver_phone": "0987654321",
    "service_type": "on-demand",
    "price": "1.00",
    "delivery_notes: "This is a test order",
    "dropoff_location": "24.7,46.6",
    "dropoff_time": "2018-10-05 12:50 AM"
  }

```

###### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

{
  "id": 319,
  "created_at": "2017-11-24T08:16:02.616730Z",
  "owner": "owner@admin.com",
  "service_type": "on-demand",
  "pickup_location": "24.7,46.6",
  "dropoff_location": "24.7,46.6",
  "receiver_name": "John",
  "receiver_phone": "+966987654321",
  "pickup_time": "2018-10-04T00:50:00.000000Z",
  "dropoff_time": "2018-10-05T00:50:00.000000Z",
  "items": "food",
  "payment_type": "COD",
  "cod_fees": 5,
  "status": "Canceled",
  "status_code": 11,
  "price": "1.00",
  "delivery_notes: "This is a test order",
  "addons": {
    "less_fees": 0,
    "packaging": 0,
    "container": 0,
    "insurance": 0,
    "additional_services": 0
  },
  "service_cost": 4,
  "dimensions": {
    "width": 0,
    "length": 0,
    "weight": 0,
    "height": 0
  },
  "tracking_no": "428679",
  "sender": {
    "phone": "123456789",
    "full_name": "John Doe",
    "store_name": "Watch Tower"
  },
  "pickup_address": "Olaya St, Al Olaya, Riyadh 12251, Saudi Arabia",
  "dropoff_address": "Olaya St, Al Olaya, Riyadh 12251, Saudi Arabia"
}
```
## Creating Orders with a Single Store

This section describes how to create orders in your account on Pick through API.
Please make sure you have an API key to successfully create orders. If you haven't receive your API key for your account through email, you can email us at support@pick.sa.

### API Access Points

<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /orders/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> POST </td>
  </tr>
  <tr>
    <td valign="top"><strong>Parameters</strong></td>
    <td>
      <ul>
        <li><code>items</code> [String]</li>
        <li><code>payment_type</code> [String]</li>
        <li><code>pickup_location</code> [String]</li>
        <li><code>pickup_time</code> [String]</li>
        <li><code>receiver_name</code> [String]</li>
        <li><code>receiver_phone</code> [String] </li>
        <li><code>service_type</code> [String] </li>
        <li><code>price</code> [Number/Integer/Float] </li>
        <li><code>delivery_notes</code> [String] OPTIONAL</li>
        <li><code>dropoff_location</code> [String] OPTIONAL</li>
        <li><code>dropoff_time</code> [String] OPTIONAL</li>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
      <ul>
        <li><code>id</code> [Number/Integer]</li>
        <li><code>created_at</code> [String]</li>
        <li><code>owner</code> [String]</li>
        <li><code>service_type</code> [String]</li>
        <li><code>pickup_location</code> [String]</li>
        <li><code>dropoff_location</code> [String]</li>
        <li><code>receiver_name</code> [String]</li>
        <li><code>eceiver_phone</code> [String]</li>
        <li><code>pickup_time</code> [String]</li>     
        <li><code>dropoff_time</code> [Number/Integer]</li>
        <li><code>items</code> [Number/Integer]</li>
        <li><code>payment_type</code> [Number/Integer]</li>
        <li><code>cod_fees</code> [Number/Integer]</li>
        <li><code>status</code> [Number/Integer]</li>
        <li><code>status_code</code> [Number/Integer]</li>
        <li><code>delivery_notes</code> [Number/Integer]</li>
        <li><code>price</code> [Number/Integer]</li>
        <li><code>less_fees</code> [Number/Integer]</li>
        <li><code>packaging</code> [Number/Integer]</li>
        <li><code>container</code> [Number/Integer]</li>
        <li><code>insurance</code> [Number/Integer]</li>
        <li><code>additional_services</code> [Number/Integer]</li>
        <li><code>service_cost</code> [Number/Integer]</li>
        <li><code>width</code> [Number/Integer]</li>
        <li><code>length</code> [Number/Integer]</li>
        <li><code>weight</code> [Number/Integer]</li>
        <li><code>height</code> [Number/Integer]</li>
        <li><code>tracking_no</code> [Number/Integer]</li>
        <li><code>phone</code> [Number/Integer]</li>
        <li><code>full_name</code> [Number/Integer]</li>
        <li><code>store_name</code> [Number/Integer]</li>
        <li><code>pickup_address</code> [Number/Integer]</li>
        <li><code>dropoff_address</code> [Number/Integer]</li>      
      </ul>
    </td>
  </tr>
</table>


#### Example

###### Request

```
POST /orders/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: {your-api-key}

Payload:
  {
    "items": "food",
    "payment_type": "COD",
    "pickup_location": "24.7,46.6",
    "pickup_time": "2018-10-04 12:50 AM",
    "receiver_name": "John Doe",
    "receiver_phone": "0987654321",
    "service_type": "on-demand",
    "price": "1.00",
    "delivery_notes: "This is a test order",
    "dropoff_location": "24.7,46.6",
    "dropoff_time": "2018-10-05 12:50 AM"
  }

```

###### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

{
  "id": 319,
  "created_at": "2017-11-24T08:16:02.616730Z",
  "owner": "owner@admin.com",
  "service_type": "on-demand",
  "pickup_location": "24.7,46.6",
  "dropoff_location": "24.7,46.6",
  "receiver_name": "John",
  "receiver_phone": "+966987654321",
  "pickup_time": "2018-10-04T00:50:00.000000Z",
  "dropoff_time": "2018-10-05T00:50:00.000000Z",
  "items": "food",
  "payment_type": "COD",
  "cod_fees": 5,
  "status": "Canceled",
  "status_code": 11,
  "price": "1.00",
  "delivery_notes: "This is a test order",
  "addons": {
    "less_fees": 0,
    "packaging": 0,
    "container": 0,
    "insurance": 0,
    "additional_services": 0
  },
  "service_cost": 4,
  "dimensions": {
    "width": 0,
    "length": 0,
    "weight": 0,
    "height": 0
  },
  "tracking_no": "428679",
  "sender": {
    "phone": "123456789",
    "full_name": "John Doe",
    "store_name": "Watch Tower"
  },
  "pickup_address": "Olaya St, Al Olaya, Riyadh 12251, Saudi Arabia",
  "dropoff_address": "Olaya St, Al Olaya, Riyadh 12251, Saudi Arabia"
}
```

## Retrieving Orders

This section describes how to retrieve orders on Pick through API.
Please make sure you have an API key to successfully retrieve an order. If you haven't receive your API key for your account through email, you can email us at support@pick.sa.

### API Access Points
#### Retrieve order details
You can get order details using this API Access Point.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /orders/{order-id} </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
      <ul>
        <li><code>id</code> [Number/Integer]</li>
        <li><code>created_at</code> [String]</li>
        <li><code>owner</code> [String]</li>
        <li><code>service_type</code> [String]</li>
        <li><code>pickup_location</code> [String]</li>
        <li><code>dropoff_location</code> [String]</li>
        <li><code>receiver_name</code> [String]</li>
        <li><code>eceiver_phone</code> [String]</li>
        <li><code>pickup_time</code> [String]</li>     
        <li><code>dropoff_time</code> [Number/Integer]</li>
        <li><code>items</code> [String]</li>
        <li><code>payment_type</code> [String]</li>
        <li><code>cod_fees</code> [Number/Integer]</li>
        <li><code>status</code> [String]</li>
        <li><code>status_code</code> [Number/Integer]</li>
        <li><code>delivery_notes</code> [String]</li>
        <li><code>price</code> [Number/Integer]</li>
        <li><code>less_fees</code> [Number/Integer]</li>
        <li><code>packaging</code> [Number/Integer]</li>
        <li><code>container</code> [Number/Integer]</li>
        <li><code>insurance</code> [Number/Integer]</li>
        <li><code>additional_services</code> [Number/Integer]</li>
        <li><code>service_cost</code> [Number/Integer]</li>
        <li><code>width</code> [Number/Integer]</li>
        <li><code>length</code> [Number/Integer]</li>
        <li><code>weight</code> [Number/Integer]</li>
        <li><code>height</code> [Number/Integer]</li>
        <li><code>tracking_no</code> [String]</li>
        <li><code>phone</code> [String]</li>
        <li><code>full_name</code> [String]</li>
        <li><code>store_name</code> [String]</li>
        <li><code>pickup_address</code> [String]</li>
        <li><code>dropoff_address</code> [String]</li>      
      </ul>
    </td>
  </tr>
</table>

#### Example


##### Request

```
GET /orders/320/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: {your-api-key}

```

##### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

  {
    "id": 320,
    "created_at": "2017-11-24T10:57:44.740410Z",
    "owner": "owner@admin.com",
    "service_type": "on-demand",
    "pickup_location": "24.7,46.6",
    "dropoff_location": null,
    "receiver_name": "John",
    "receiver_phone": "0987654321",
    "pickup_time": "2018-10-04T00:50:00.000000Z",
    "dropoff_time": null,
    "items": "food",
    "payment_type": "COD",
    "cod_fees": 5,
    "status": "Initiated",
    "status_code": 0,
    "delivery_notes": null,
    "price": "0.00",
    "addons": {
      "less_fees": 0,
      "packaging": 0,
      "container": 0,
      "insurance": 0,
      "additional_services": 0
    },
    "service_cost": 34,
    "dimensions": {
      "width": 0,
      "length": 0,
      "weight": 0,
      "height": 0
    },
    "tracking_no": "245333",
    "sender": {
      "phone": "0987654321",
      "full_name": "John Doe",
      "store_name": "Test Store"
    },
    "pickup_address": "Olaya St, Al Olaya, Riyadh 12251, Saudi Arabia",
    "dropoff_address": null
  }
```

#### Retrieve ALL orders details
You can get all your orders using this API Access Point.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /orders/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
    List of orders with the following details:
      <ul>
        <li><code>id</code> [Number/Integer]</li>
        <li><code>created_at</code> [String]</li>
        <li><code>owner</code> [String]</li>
        <li><code>service_type</code> [String]</li>
        <li><code>pickup_location</code> [String]</li>
        <li><code>dropoff_location</code> [String]</li>
        <li><code>receiver_name</code> [String]</li>
        <li><code>eceiver_phone</code> [String]</li>
        <li><code>pickup_time</code> [String]</li>     
        <li><code>dropoff_time</code> [Number/Integer]</li>
        <li><code>items</code> [String]</li>
        <li><code>payment_type</code> [String]</li>
        <li><code>cod_fees</code> [Number/Integer]</li>
        <li><code>status</code> [String]</li>
        <li><code>status_code</code> [Number/Integer]</li>
        <li><code>delivery_notes</code> [String]</li>
        <li><code>price</code> [Number/Integer]</li>
        <li><code>less_fees</code> [Number/Integer]</li>
        <li><code>packaging</code> [Number/Integer]</li>
        <li><code>container</code> [Number/Integer]</li>
        <li><code>insurance</code> [Number/Integer]</li>
        <li><code>additional_services</code> [Number/Integer]</li>
        <li><code>service_cost</code> [Number/Integer]</li>
        <li><code>width</code> [Number/Integer]</li>
        <li><code>length</code> [Number/Integer]</li>
        <li><code>weight</code> [Number/Integer]</li>
        <li><code>height</code> [Number/Integer]</li>
        <li><code>tracking_no</code> [String]</li>
        <li><code>phone</code> [String]</li>
        <li><code>full_name</code> [String]</li>
        <li><code>store_name</code> [String]</li>
        <li><code>pickup_address</code> [String]</li>
        <li><code>dropoff_address</code> [String]</li>      
      </ul>
    </td>
  </tr>
</table>

#### Example


##### Request

```
GET /orders/
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
    "id": 320,
    "created_at": "2017-11-24T10:57:44.740410Z",
    "owner": "patrick@pick.sa",
    "service_type": "on-demand",
    "pickup_location": "24.7,46.6",
    "dropoff_location": null,
    "receiver_name": "John",
    "receiver_phone": "0987654321",
    "pickup_time": "2018-10-04T00:50:00.000000Z",
    "dropoff_time": null,
    "items": "food",
    "payment_type": "COD",
    "cod_fees": 5,
    "status": "Initiated",
    "status_code": 0,
    "delivery_notes": null,
    "price": "0.00",
    "addons": {
      "less_fees": 0,
      "packaging": 0,
      "container": 0,
      "insurance": 0,
      "additional_services": 0
    },
    "service_cost": 34,
    "dimensions": {
      "width": 0,
      "length": 0,
      "weight": 0,
      "height": 0
    },
    "tracking_no": "245333",
    "sender": {
      "phone": "",
      "full_name": "",
      "store_name": ""
    },
    "pickup_address": "Olaya St, Al Olaya, Riyadh 12251, Saudi Arabia",
    "dropoff_address": null
  },
  {
    "id": 319,
    "created_at": "2017-11-24T08:16:02.616730Z",
    "owner": "patrick@pick.sa",
    "service_type": "on-demand",
    "pickup_location": "24.7,46.6",
    "dropoff_location": null,
    "receiver_name": "John",
    "receiver_phone": "+966987654321",
    "pickup_time": "2018-10-04T00:50:00.000000Z",
    "dropoff_time": null,
    "items": "food",
    "payment_type": "COD",
    "cod_fees": 5,
    "status": "Canceled",
    "status_code": 11,
    "delivery_notes": null,
    "price": "0.00",
    "addons": {
      "less_fees": 0,
      "packaging": 0,
      "container": 0,
      "insurance": 0,
      "additional_services": 0
    },
    "service_cost": 4,
    "dimensions": {
      "width": 0,
      "length": 0,
      "weight": 0,
      "height": 0
    },
    "tracking_no": "428679",
    "sender": {
      "phone": "123456789",
      "full_name": "Patrick Concepcion",
      "store_name": "Watch Tower"
    },
    "pickup_address": "Olaya St, Al Olaya, Riyadh 12251, Saudi Arabia",
    "dropoff_address": null
  }
]
```

## Cancelling Orders

This section describes how to cancel an order on Pick through API.
Please make sure you have an API key to successfully cancel an order. If you haven't receive your API key for your account through email, you can email us at support@pick.sa.

### API Access Points
You can cancel an order using this API Access Point.
<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /order/{order-id}/cancel/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> POST </td>
  </tr>
</table>


#### Example

##### Request

```
POST /orders/2/cancel/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: {your-api-key}
```

##### Success Response

```
HTTP/1.0 204 OK 
```
