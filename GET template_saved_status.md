#### `<GET> http://140.131.115.99/api/template/saved/{template_id}`

用途：顯示使用者是否有收藏此模板

---

* Return Values

```yaml
{"saved":"0"}
```

    >* 0：沒收藏 
    >* 1：有收藏

---

* Examples

顯示使用者是否有收藏template_id為1的模板

```html
http://140.131.115.99/api/template/saved/1
```

* Above example will output

```yaml
{"saved":"0"}
```