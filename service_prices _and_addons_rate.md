# Service Prices and Addons Rate
For testing purposes, please use `https://sandbox.pick.sa/` to retrieve your service prices and addons rate.<br>
For example: `https://sandbox.pick.sa/users/prices/`

## Introduction
This document explains on how to set and retrieve your account's service prices and addons rate.<br>
We have **three types** of **service** and **four addons** that you can avail. Below are the description for each.<br>
If you have questions, you can email us at info@pick.sa .
<br><br>

<table>
  <tr>
    <td colspan=2><strong>SERVICE</strong></td>
  </tr>
  <tr>
    <td>On Demand</td>
    <td> <b>Same-city and same-day delivery</b> - The delivery could be delivered around 3 to 12 hours.</td>
  </tr>
  <tr>
    <td>Economy</td>
    <td><b>Same-city delivery</b> - We will pick up the parcel within 24 hours and deliver it within 48 hrs after we pick up the parcel.</td>
  </tr>
  <tr>
    <td>Shipping</td>
    <td><b>Cross-city delivery</b> - The delivery process will take 2 to 4 business days.</td>
  </tr>
</table>

<table>
  <tr>
    <td colspan=2><strong>ADDONS</strong></td>
  </tr>
  <tr>
    <td>Packaging</td>
    <td>Additional payment for the packaging of the parcel.</td>
  </tr>
  <tr>
    <td>Container</td>
    <td>Additional payment for the container of the parcel.</td>
  </tr>
  <tr>
    <td>Insurance</td>
    <td>Addititonal payment for the insurance of the parcel.</td>
  </tr>
  <tr>
    <td>COD</td>
    <td>Additional payment if the delivery is Cash on Delivery.</td>
  </tr>
</table>


## Service Prices and Addons Rate
We have default service prices and addons rate for our customer. If you want custom service prices from our services, you can email us at
operations@pick.sa for more information.

<table>
  <tr>
    <td><strong>SERVICE</strong></td>
    <td><strong>PRICE (SAR)</strong></td>
  </tr>
  <tr>
    <td>On Demand</td>
    <td>34 SAR</td>
  </tr>
  <tr>
    <td>Economy</td>
    <td>24 SAR</td>
  </tr>
  <tr>
    <td>Shipping</td>
    <td>26 SAR</td>
  </tr>
</table>

<table>
  <tr>
    <td><strong>ADDONS</strong></td>
    <td><strong>PRICE (SAR)</strong></td>
  </tr>
  <tr>
    <td>Packaging</td>
    <td>5 SAR</td>
  </tr>
  <tr>
    <td>Container</td>
    <td>5 SAR</td>
  </tr>
  <tr>
    <td>Insurance</td>
    <td>25 SAR</td>
  </tr>
  <tr>
    <td>COD</td>
    <td>5 SAR</td>
  </tr>
</table>

## Retrieving Service Prices and Addons Rate

This section describes how to retrieve service prices and rates on Pick through API.
Please make sure you have an API key to successfully create a merchant. If you haven't receive your API key for your account through email, you can email us at support@pick.sa.

### API Access Points

<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /users/prices/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> GET </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
      <ul>
        <li><code>on-demand</code> [Number/Integer/Float]
        <li><code>economy</code> [Number/Integer/Float]
        <li><code>shipping</code> [Number/Integer/Float]
        <li><code>packaging</code> [Number/Integer/Float]
        <li><code>container</code> [Number/Integer/Float]
        <li><code>insurance</code> [Number/Integer/Float]
        <li><code>COD</code> [Number/Integer/Float]
      </ul>
    </td>
  </tr>
</table>


#### Example

###### Request

```
POST /users/prices/
Host: sandbox.pick.sa
Content-Type: application/json
x-api-key: {your-api-key}

```

###### Success Response

```
HTTP/1.0 200 OK 
Content-Type: application/json

{
  "service_prices": {
    "on-demand": 34,
    "shipping": 26,
    "economy": 24
  },
  "addon_prices": {
    "packaging": 5,
    "container": 5,
    "insurance": 25,
    "COD": 5
  }
}
```
