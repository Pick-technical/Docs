# Airway bill
For testing purposes, please use `https://sandbox.pick.sa/` to retrieve the airway bill.<br>
For example: `https://sandbox.pick.sa/orders/{id}/airway_bill/`
<br><br>
This document explains on how to retrieve airway bill in your orders.
## Retrieving Airway bill

This section describes on how to retrieve airway bill on Pick through API.
Please make sure you have an API key to successfully retrieve an airway bill. If you haven't receive your API key for your account through email, you can email us at support@pick.sa.

### API Access Points

<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /orders/{order-id}/airway_bill/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
  </tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
      {pdf file}
    </td>
  </tr>
</table>


#### Example

###### Request

```
POST /orders/1/airway_bill/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: {your-api-key}
```

###### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

  {pdf file}
```
