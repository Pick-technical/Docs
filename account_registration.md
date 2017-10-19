# Account Registration

## Introduction

This document describes how to register an account on Pick through API.


## API Access Points

<table>
  <tr>
    <td><strong>URL</strong></td>
    <td> /auth/registration/ </td>
  </tr>
  <tr>
    <td><strong>HTTP Method</strong></td>
    <td> POST </td>
  </tr>
  <tr>
    <td valign="top"><strong>Parameters</strong></td>
    <td>
      <ul>
        <li><code>email</code> [String] It should be a valid email.
        <li><code>password1</code> [String]
        <li><code>password2</code> [String] Should match to <code>password1</code>.
        <li><code>phone</code> [String]
        <li><code>store_url</code> [String]
        <li><code>gender</code> [String] Choose one: <code>male</code> or <code>female</code>
      </ul>
    </td>
  </tr>
  <tr>
    <td valign="top"><strong>Response</strong></td>
    <td>
      <ul>
        <li><code>key</code> [String]
      </ul>
    </td>
  </tr>
</table>


## Example

For testing purposes, use `https://sandbox.pick.sa/` to create an account.


#### Request

```
POST /auth/registration/
Host: sandbox.pick.sa
Content-Type: application/json

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

{ key: 1234567890asdfghjkl }
```

If you receive this response, then the next step is to verify your account via email to complete the registration.
