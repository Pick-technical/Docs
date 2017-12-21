# Order Status and Status Codes

This document contains the list of status and status codes of the Order.

### Sample Payload:

```
{"action":"statusUpdate","data":{"id":1234,
"created_at":"2017-01-01T00:00:00Z",
"owner":"test@test.com",
"service_type":"shipping",
"pickup_location":"24.7,46.7",
"dropoff_location":"19.123,37.81",
"receiver_name":"test​ ​ name",
"receiver_phone":"507548762",
"pickup_time":"2018-01-01T00:00:00",
"dropoff_time":"2019-01-01T00:00:00",
"items":"other",
"payment_type":"COD",
"cod_fees":5,
"status":"Delivered",
"status_code":​ ​ 10,
"delivery_notes":null,
"price":"1.00",
"addons":{"packaging":0,"less_fees":4,"container":0,"insurance":0,"ad
ditional_services":0},
"service_cost":29.0,
"dimensions":{"width":0,"length":0,"weight":0,"height":0},"tracking_no":"123456",
"sender":{"phone":"1234567","full_name":"test
name","store_name":"Test​ ​ store"},
"pickup_address":"Test​ ​ address",
"dropoff_address":"Buyer​ ​ Test​ ​ address",
"merchant":{"id":1,"first_name":"test","last_name":"name","store_name":"Test​ ​ store",
"location":"24.7,​ ​ 46.7","url":"https://test.test",
"phone":"123456789","owner":"test@test.com","date_created":"2017-01-0
1T00:00:00.00Z"}}}
```

<table>
  <tr>
    <td><strong>Code</strong></td>
    <td><strong>Status Name</strong></td>
    <td><strong>Description</strong></td>
  </tr>
  <tr>
    <td>0</td>
    <td>Initiated</td>
    <td>The order has been created.</td>
  </tr>
  <tr>
    <td>1</td>
    <td>Waiting Receiver Action</td>
    <td>waiting for the receiver(buyer) to confirm his location.</td>
  </tr>
  <tr>
    <td>2</td>
    <td>Receiver Location is updated</td>
    <td>receiver(buyer) already confirm his location.</td>
  </tr>
  <tr>
    <td>3</td>
    <td>Waiting Picker Action</td>
    <td>waiting to assign picker.</td>
  </tr>
  <tr>
    <td>4</td>
    <td>Picker assigned to Pick up</td>
    <td>a picker is already assigned to pick up the order.</td>
  </tr>
  <tr>
    <td>5</td>
    <td>Out for Pick up</td>
    <td>picker is ready to pickup the order and is on the way.</td>
  </tr>
  <tr>
    <td>6</td>
    <td>Picked up</td>
    <td>Order is already picked up by the picker.</td>
  </tr>
  <tr>
    <td>7</td>
    <td>Arrived at Pick warehouse</td>
    <td>Order arrives at pick warehouse.</td>
  </tr>
  <tr>
    <td>8</td>
    <td>Arrived at destination Warehouse</td>
    <td>Order arrives at the destination warehouse.</td>
  </tr>
  <tr>
    <td>9</td>
    <td>Out for delivery</td>
    <td>Currently delivering the order.</td>
  </tr>
  <tr>
    <td>10</td>
    <td>Delivered</td>
    <td>Delivery successful.</td>
  </tr>
  <tr>
    <td>11</td>
    <td>Canceled</td>
    <td>Delivery got canceled.</td>
  </tr>
</table>
