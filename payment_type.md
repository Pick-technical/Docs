# Payment Types

This document is to explain Payment Types in creating an order.
<br><br>
Payment Type determines how the payment will be handled on Pick.This section will tell you more information about payment type
and the computation that will happen for the prices.
<br><br>
For this let us define some terminologies:
<table>
  <tr>
    <td><b>Item Price</b></td>
    <td> The price of the parcel.</td>
  </tr>
  <tr>
    <td><b>Service Price</b></td>
    <td>The service charge for the delivery.</td>
  </tr>
  <tr>
    <td><b>Addons Price</b></td>
    <td>The price for the addons (packaging, container, insurance, etc.) of the delivery.</td>
  </tr>
</table>

<br>
After learning the terminologies, we can now proceed to the Payment Types:
<table>
  <tr>
    <td><strong>Payment Type</strong></td>
    <td><strong>Price</strong></td>
    <td><strong>Description</strong></td>
  </tr>
  <tr>
    <td>COD</td>
    <td>Item Price + Service Price + Addons Price</td>
    <td>Cash on Delivery. This means that the buyer must pay the price indicated to the delivery man upon delivery. All expenses will be paid
    by the buyer.</td>
  </tr>
  <tr>
    <td>pre-paid</td>
    <td>Already paid</td>
    <td>This means that the buyer already paid the price in advance to the seller. The buyer pays all the expenses.</td>
  </tr>
  <tr>
    <td>only_sender_fees</td>
    <td>Service Price + Addons Price</td>
    <td>This means that the buyer must pay the price indicated to the delivery man upon delivery. The buyer will only pay
    service price and addons price to the delivery man.</tr>
  <tr>
    <td>only_receiver_fees</td>
    <td>Item Price</td>
    <td>This means that the buyer will only pay for the item price upon delivery.</td>
  </tr>
</table>
