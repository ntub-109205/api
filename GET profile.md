#### `<GET> http://140.131.115.99/api/profile`

用途：顯示使用者名稱

---

* Return Values

```yaml
{
    "name": ${username}
}
```

---

* Examples

```html
http://140.131.115.99/api/login
```

* Above example will output

```yaml
{
    "name": "kevin"
}
```

>* 代表現在登入的使用者名稱為kevin
