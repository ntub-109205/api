#### `<POST> http://140.131.115.99/api/template/store`

用途：上傳模板圖片

>* 需搭配api : template_txt_store

* Parameters

|key  |type            |
|-----|----------------|
|image|required;jpg;png|

>* required為必要

---

* Return Values

```yaml
{"success":"your posts has been successfully saved!","template_id":${template_id}}
```

>* template_id為上傳成功後，該模板所回傳的template_id

---

* Examples

```html
http://140.131.115.99/api/template/store

image = 比讚貓咪2.jpg
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!","template_id":3}
```

>* 比讚貓咪2.jpg的模板id為3