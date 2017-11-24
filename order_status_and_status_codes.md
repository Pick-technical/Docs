# Order Status and Status Codes

This document contains the list of status and status codes of the Order.

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
