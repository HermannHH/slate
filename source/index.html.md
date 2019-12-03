---
title: API Documentation
language_tabs:
  - json: JSON
  - shell: cURL
---


# Api::V1::Sessions



## when user details are correct


### Request

#### Endpoint

```plaintext
POST /api/v1/sessions
Host: example.org
Content-Type: application/x-www-form-urlencoded
Cookie:
```

`POST /api/v1/sessions`

#### Parameters


```json
email=foo%40bar.com&password=foobar
```


| Name | Description |
|:-----|:------------|
| email *required* | Email of user |
| password *required* | Password of user |



### Response

```plaintext
X-Frame-Options: SAMEORIGIN
X-XSS-Protection: 1; mode=block
X-Content-Type-Options: nosniff
X-Download-Options: noopen
X-Permitted-Cross-Domain-Policies: none
Referrer-Policy: strict-origin-when-cross-origin
Content-Type: application/json; charset=utf-8
ETag: W/&quot;fafe669a9fb817d51e3c1b554cb78944&quot;
Cache-Control: max-age=0, private, must-revalidate
X-Request-Id: 962b4606-41cc-4bb8-bd94-5af56c3fe0ac
X-Runtime: 0.048784
Content-Length: 122
200 OK
```


```json
{
  "auth_token": "eyJhbGciOiJIUzI1NiJ9.eyJ1c2VyX2lkIjoxLCJleHAiOjE1NzU0ODM4NTV9.iEl3eb9A1VDhIWpJIRF4ACisRwvjKn-VIemyVOGEXPY"
}
```



## when user details are incorrect


### Request

#### Endpoint

```plaintext
POST /api/v1/sessions
Host: example.org
Content-Type: application/x-www-form-urlencoded
Cookie:
```

`POST /api/v1/sessions`

#### Parameters


```json
email=nonexist%40mail.com&password=toets
```


| Name | Description |
|:-----|:------------|
| email *required* | Email of user |
| password *required* | Password of user |



### Response

```plaintext
X-Frame-Options: SAMEORIGIN
X-XSS-Protection: 1; mode=block
X-Content-Type-Options: nosniff
X-Download-Options: noopen
X-Permitted-Cross-Domain-Policies: none
Referrer-Policy: strict-origin-when-cross-origin
Content-Type: application/json; charset=utf-8
Cache-Control: no-cache
X-Request-Id: e1e4b0c2-dc0a-488b-afa1-c74afe237d1c
X-Runtime: 0.045999
Content-Length: 33
401 Unauthorized
```


```json
{
  "message": "Invalid credentials"
}
```



