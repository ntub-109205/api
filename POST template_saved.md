#### `<POST> http://140.131.115.99/api/template/saved`

用途：收藏(取消收藏)模板

* Parameters

|key        |type                |
|--------   |--------------------|
|template_id|required;template_id|

>* required為必要
>* 若資料庫沒有該template_id則會返回錯誤訊息

---

* Return Values

```yaml
{"saved":${boolean}}
```

>* 回傳值為收藏後的狀態

---

* Examples (1)

收藏template_id為1的模板

```html
http://140.131.115.99/api/template/saved

template_id = 1
```

* Above example will output

```yaml
{"saved":"1"}
```

---

* Examples (2)

取消收藏template_id為1的模板

```html
http://140.131.115.99/api/template/saved

template_id = 1
```

* Above example will output

```yaml
{"saved":"0"}
```