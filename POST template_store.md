#### `<POST> http://140.131.115.99/api/template/store`

用途：上傳模板圖片

>* 需先使用api : [txt store](https://github.com/ntub-109205/api/blob/master/POST%20txt_store.md)

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

上傳公開的梗圖模板

* execute [txt store](https://github.com/ntub-109205/api/blob/master/POST%20txt_store.md)

```html
http://140.131.115.99/api/txt/store

category_id = 1
share       = 1
name        = example
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!"}
```

* then execute template store api

```html
http://140.131.115.99/api/template/store

image = 比讚貓咪2.jpg
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!","template_id":3}
```

>* 比讚貓咪2.jpg的模板id為3