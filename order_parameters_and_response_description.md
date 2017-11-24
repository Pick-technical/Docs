# Orders Parameters and Response Description

## Order Parameters
This document explains the order parameters and order description in the order request.

<table>
  <tr>
    <td><strong>Parameter Name</strong></td>
    <td><strong>Description</strong></td>
    <td><strong>Value</strong></td>
  </tr>
  <tr>
    <td>items</td>
    <td>The type of parcel to be delivered.</td>
    <td><i>[String]</i><br><b>CHOICES:</b> [ FOOD, ELECTRONICS, CLOTHING, MAKEUP, HEALTH_CARE, HOUSEHOLD, OTHER ]</td>
  </tr>
  <tr>
    <td>payment_type</td>
    <td>How the parcel will be paid. For more information click <a href="">here</a>.</td>
    <td><i>[String]</i><br><b>CHOICES :</b> [ cod, pre-paid, only_sender_fees, only_receiver_fees ]</td>
  </tr>
  <tr>
    <td>pickup_location</td>
    <td>The location of your store where we will pickup the parcel.</td>
    <td><i>[String]</i> This should be a coordinate. For example: "24.6, 46.7"</td>
  </tr>
  <tr>
    <td>pickup_time</td>
    <td>What time the delivery man will pickup the parcel to your store.</td>
    <td><i>[String]</i> Format should be: `YYYY-MM-DD hh:mm [AM|PM]`</td>
  </tr>
  <tr>
    <td>receiver_name</td>
    <td>The name of the buyer.</td>
    <td><i>[String]</i></td>
  </tr>
  <tr>
    <td>receiver_phone</td>
    <td>The phone number of the buyer.</td>
    <td><i>[String]</i></td>
  </tr>
  <tr>
    <td>service_type</td>
    <td>The type of service for the order. The default service type is `on-demand`. Different fees will be applied depending on the service choosen.For more information click <a href="https://github.com/Pick-technical/Docs/blob/master/service_prices%20_and_addons_rate.md">here</a></td>
    <td><i>[String</i><br><b>CHOICES :</b> [ on-demand, economy, shipping ]</td>
  </tr>
    <tr>
    <td>dropoff_location <b>[OPTIONAL]</b></td>
    <td>The location of the buyer where the delivery man will deliver the package.</td>
      <td><i>[String]</i> This should be a coordinate. For example: "24.6, 46.7"</td>
  </tr>
  <tr>
    <td>dropoff_time <b>[OPTIONAL]</b></td>
    <td>The time the delivery man should deliver the package to the buyer.</td>
    <td><i>[String]</i> Format should be: `YYYY-MM-DD hh:mm [AM|PM]`</td>
  </tr>
  <tr>
    <td>price</td>
    <td>The price of the parcel.</td>
    <td><i>[Integer/Float]</i></td>
  </tr>
  <tr>
    <td>delivery_notes <b>[OPTIONAL]</b></td>
    <td>The notes of the user for the delivery.</td>
    <td><i>[String]</i></td>
  </tr>
  </table>
  
## Order Response

<table>
  <tr>
    <td><strong>Response Name</strong></td>
    <td><strong>Description</strong></td>
  </tr>
  <tr>
    <td>id</td>
    <td>The id of the order. {order-id}</td>
  </tr>
  <tr>
    <td>created_at</td>
    <td>The time the order is created.</td>
  </tr>
  <tr>
    <td>owner</td>
    <td>The email of the owner.</td>
  </tr>
  <tr>
    <td>items</td>
    <td>The type of parcel to be delivered.</td>
  </tr>
  <tr>
    <td>payment_type</td>
    <td>How the parcel will be paid.</td>
  </tr>
  <tr>
    <td>pickup_location</td>
    <td>The location of your store where we will pickup the parcel.</td>
  </tr>
  <tr>
    <td>pickup_time</td>
    <td>What time the delivery man will pickup the parcel to your store.</td>
  </tr>
  <tr>
    <td>receiver_name</td>
    <td>The name of the buyer.</td>
  </tr>
  <tr>
    <td>receiver_phone</td>
    <td>The phone number of the buyer.</td>
  </tr>
  <tr>
    <td>service_type</td>
    <td>The type of service for the order. Different fees will be applied depending on the service choosen.</td>
  </tr>
    <tr>
    <td>dropoff_location</td>
    <td>The location of the buyer where the delivery man will deliver the package.</td>
  </tr>
  <tr>
    <td>dropoff_time</td>
    <td>The time the delivery man should deliver the package to the buyer.</td>
  </tr>
  <tr>
    <td>price</td>
    <td>The price of the parcel.</td>
  </tr>
  <tr>
    <td>delivery_notes</td>
    <td>The notes of the user for the delivery.</td>
  </tr>
  <tr>
    <td>cod_fees</td>
    <td>The fee if the delivery is Cash On Delivery.</td>
  </tr>
  <tr>
    <td>status</td>
    <td>The status of the delivery.For more information click <a href="">here</a></td>
  </tr>
  <tr>
    <td>status_code</td>
    <td>The status code of the delivery.For more information click <a href="">here</a></td>
  </tr>
  <tr>
    <td>packaging</td>
    <td>An addons fee for the packaging of the delivery.</td>
  </tr>
  <tr>
    <td>container</td>
    <td>An addons fee for the container of the delivery.</td>
  </tr>
  <tr>
    <td>insurance</td>
    <td>An addons fee for the insurance of the delivery.</td>
  </tr>
  <tr>
    <td>service_cost</td>
    <td>The service fee for the delivery depending on the service type you choose.</td>
  </tr>
  <tr>
    <td>width</td>
    <td>The width of the parcel.</td>
  </tr>
  <tr>
    <td>length</td>
    <td>The height of the parcel.</td>
  </tr>
  <tr>
    <td>weight</td>
    <td>The weight of the parcel.</td>
  </tr>
  <tr>
    <td>height</td>
    <td>The height of the parcel.</td>
  </tr>
  <tr>
    <td>tracking_no</td>
    <td>The tracking number of the delivery.</td>
  </tr>
  <tr>
    <td>phone</td>
    <td>The contact number of the seller.</td>
  </tr>
  <tr>
    <td>full_name</td>
    <td>The full name of the seller.</td>
  </tr>
  <tr>
    <td>store_name</td>
    <td>The name of your store.</td>
  </tr>
  <tr>
    <td>pickup_address</td>
    <td>The address of your store.</td>
  </tr>
  <tr>
    <td>dropoff_address</td>
    <td>The address of the buyer.</td>
  </tr>
</table>
