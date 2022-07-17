*  [Reset Password]()
    *  [Description](#description)
    *  [Success Response](#success-response)
    *  [Error Response](#error-response)

**URL**: [/auth/resetpassword](#ErrorResponse)

**Method**: ```POST```

---

## Description

Use to reset your ```password``` in PostgreSQL Database

**Header**

```
{
  "tokenid": "'Bearer' + AccessToken : string
}
```

**Data constraints**

```
{
  "password": "password in plain text": string
}
```

**Data example**

```
{
  "password": "azerty2-",
}
```

---

## Success Response

**Code**: ```200 OK```

**Content**

```
{
    'status': 200,
    'expires_in': 'Ok',
}
```

---

## Error Response

| Status   |      Condition      | <div style="width:90px"> Response </div> |
|----------|:-------------:|------:|
| 500 |  Error with PostgreSQL Database | <pre><code class="language-json" style="text-align: left;">{<br/> status: "500",<br/> message: "500 an error was detected"<br/>}</code></pre><br/> |
| 403 |  If your ```id``` does not exist in PostgreSQL Database | <pre><code class="language-json" style="text-align: left;">{<br/> status: "403",<br/> message: "403 User not found"<br/>}</code></pre><br/> |
| 500 |  An error with the ```password``` | <pre><code class="language-json" style="text-align: left;">{<br/> status: "500",<br/> message: "500 error while generating the salt"<br/>}</code></pre><br/> |