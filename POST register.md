#### `<POST> http://140.131.115.99/api/register`

用途：註冊帳號

* Parameters

|key       |type                         |
|----------|-----------------------------|
|email     |required;email;max:255;unique|
|name      |required;max:100;unique      |
|password  |required;min:6;max:255       |
|c_password|required;same:password       |

>* required 為必要
>* email 欄位不能重覆
>* name 欄位不能重覆
>* password 字元長度需要 >= 6

---

* Return Values

```yaml
{
    "success": {
        "token": "${token}",
        "name": "${name}"
    }
}
```

---

* Examples (1)

```html
http://140.131.115.99/api/register

email      = 10836007@ntub.edu.tw
name       = 10836007
password   = example
c_password = example
```

* Above example will output

```yaml
{
    "success": {
        "token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiIxIiwianRpIjoiMzE0NzA1Y2Y3MTUyMWQzOTQwYzE0M2FkYjM3MjY3NDI5ODNkOTc2NDQyYzYyMzhmNGZhY2ViZDlmMDU1N2ZhYThkZTJjMjE4YTNkZDNiNGMiLCJpYXQiOjE2MDIzODc1ODcsIm5iZiI6MTYwMjM4NzU4NywiZXhwIjoxNjMzOTIzNTg3LCJzdWIiOiI0Iiwic2NvcGVzIjpbXX0.d1pwjUc6_v-Uv7cnyrN95YIdsBk1xZybzXx3J1J3lLDRbEqa7APwlNfG96JGHsxrJ7Dp_7Bj-uBdFsrhqHgXE5wD2x49kWlqUuXsq4Iu5ppbtj8T3G10ydT-IKthiSzSRMlCMAOW9jv3Tdl7pY9iUk2CxcAer7cBq64zD3-2SGnEYP5p_7H9g8EtUQo6O7_AKqC047z0dXGCKyIZYQhwqs2HLL3YWKuWqGOVSNe3gAA59ueVxnkkme9IqMgX5QIaI-CMISsPgutHbKY_MSxNVqu3gTA1CVCLqbUBm35jaL2LCnkyz8lpQ3V0X1kfmbJBr3hN_QCf5Y_0L7hyxl83NZDt35kippb2xAucQHC0EwcLr9UnMRHer0Lm986FeTZhlMhXS_RPJhEgLpFzo4mRieppJzlVm1Vq8MjAGf1ioApjXW-zsABEvbn-CebqKC7AYyu3eZPkzXrgiz5mJoH8lX6v5gS1-ZcKBavjqbYQdvhi1oiOvcRA4HKOkxdHwc0NfqPPjxTvOobwhZ7NHXObACzkWFRRNPLeP-A7qNkHW-VQ7HnShSGS8dUPn-pWXq6Hfhu_nGkt0-rumWhuprIMtq1aWq5Spe4MbnU0lrfVpdRVIyU4wc0lwyctrzC6m4fo9p_MWoPYTJCONg4Tm0cbFNrNM48RMd1QZ7wZAnHSUN8",
        "name": "10836007"
    }
}
```

---

* Examples (2)

```html
http://140.131.115.99/api/register

email      = 10836007@ntub.edu.tw
name       = 10836007
password   = 123
c_password = 124
```

* Above example will output
```yaml
{
    "error": {
        "name": [
            "The name has already been taken."
        ],
        "email": [
            "The email has already been taken."
        ],
        "password": [
            "The password must be at least 6 characters."
        ],
        "c_password": [
            "The c password and password must match."
        ]
    }
}
```