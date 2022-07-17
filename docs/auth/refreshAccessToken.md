*  [Reset Password]()
    *  [Description](#description)
    *  [Success Response](#success-response)
    *  [Error Response](#error-response)

**URL**: [/auth/refreshaccesstoken](#ErrorResponse)

**Method**: ```GET```

---

## Description

Use to refresh your access token in PostgreSQL Database

**Header**

```
{
  "tokenid": "'Bearer' + RefreshToken" : string
}
```

---

## Success Response

**Code**: ```200 OK```

**Content**

```
{
    'accessToken': RjY2NjM5NzA2OWJjuE7c,
    'expires_in': '1800s',
    'tokenType': 'Bearer'
}
```

---

## Error Response

| Status   |      Condition      | <div style="width:90px"> Response </div> |
|----------|:-------------:|------:|
| 500 |  Error with jwt | <pre><code class="language-json" style="text-align: left;">{<br/> status: "401",<br/> message: "401 jwt not found"<br/>}</code></pre><br/> |