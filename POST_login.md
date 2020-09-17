#### `<POST> http://140.131.115.99/api/login`

用途：登入

* Parameters

|key     |type           |
|--------|---------------|
|email   |required;email |
|password|required;string|

>* required為必要

---

* Return Values

```yaml
{
    "success": {
        "token": ${token}
    }
}
```

---

* Examples

``` html
http://140.131.115.99/api/login

email    = example@example.com
password = passwd
```

* Above example will output

```yaml
{
    "success": {
        "token": "dfJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiJ9.eyJhdWQiOiIxIiwianRpIjoiMzVmNTZiZWRlZGUyNTI2OWMyZmE1NDc1MTc2YmNiOGNkNTc5NDliMjQwYTQwM2EwZmJjN2JlNjBlMTYwZGNjNmFkMzAxYTFjMzQ0NzY1M2YiLCJpYXQiOjE2MDAzNTAzMDcsIm5iZiI6MTYwMDM1MDMwNywiZXhwIjoxNjMxODg2MzA3LCJzdWIiOiIyIiwic2NvcGVzIjpbXX0.mAlO5KkW7lA-UQnQnpODYa8PmC4V8xkiK8sfT2ZVkYgn46vMhCzG7AztnO5QaVaUAv0Ci-idDm4i_-OblkH71q4TcfLZ3PpMb_dzrtX7zj90Lu5Md8m5lQFqMOM97dewqk5-1AzsLqz5r2lry70m5jNaEFuDxD8lGeaQ7HwqcQ6kItIecF1cxtjLEvkFZvt8eyDZILLD7DKcKLV13uIErEkK5HMqnHIOIihyFqSSrFBU9BxjBbkIg4at8QMPwSUAYtL0iX8gF07H-FTScN-GlPvCpBuiFyTYdLo1Up1smZBpn_N6X2okAqmAa4pWK9Hx47lihffEoQq3RCyosVRq2K9DQJ4zoitJN5vYvBOm96spUWISIcuAsp-fzh90--gHYQOC5Uxs_5txjh6yeKc8UGgVh8ePRV9ii72gn6ECy6llqPa-3_ZEj0WZVSPsape1PK3Qp_rSJY_Q0z0WpR6fquC8AJq7KegkgoPk_zCuaUGBw6A5y6ZLHM0XRR2tOfD1PsPVERoW7mWc-aRNnDgIynNjjWi-3H3_he-G7RJQgO8lUUkiGgaxfj8dyIlQ3yO_qUOVgRKOLH_ejqqlfOvqadCz6zML0BtaWiB62DGSl1ywhIFU59klxaHhHvDGLFL5DoAj7-Bmz7IiKApFXI2ZtXfxp3RAU8inMggdP7pSfjVU"
    }
}
```