*  [Register]()
    *  [Description](#description)
    *  [Success Response](#success-response)
    *  [Error Response](#error-response)

**URL**: [/auth/register]()

**Method**: ```POST```

---

## Description

Use to create a user in PostgreSQL Database with ```email``` and ```password```

**Data constraints**

```
{
  "email": "valid email address": string,
  "password": "password in plain text": string
}
```

**Data example**

```
{
  "email": "kylianG@gmail.com",
  "password": "azerty2-",
}
```

---

## Success Response

**Code**: ```200 OK```

**Content**

```
{
    'refreshToken': AYjcyMzY3ZDhiNmJkNTY,
    'accessToken': RjY2NjM5NzA2OWJjuE7c,
    'expires_in': '1800s',
    'tokenType': 'Bearer'
}
```

---

## Error Response

| Status   |      Condition      | <div style="width:90px"> Response </div> |
|::|::|::|
| 403 |  If your ```email``` already exist in PostgreSQL Database | <pre><code class="language-json" style="text-align: left;">{<br/> status: "403",<br/> message: "403 Your email already exists"<br/>}</code></pre><br/> |
| 500 |  Error with PostgreSQL Database | <pre><code class="language-json" style="text-align: left;">{<br/> status: "500",<br/> message: "500 an error was detected"<br/>}</code></pre><br/> |
| 500 |  An error with the password | <pre><code class="language-json" style="text-align: left;">{<br/> status: "500",<br/> message: "500 error while generating the salt"<br/>}</code></pre><br/> |