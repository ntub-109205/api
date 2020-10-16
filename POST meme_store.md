#### `<POST> http://140.131.115.99/api/meme/store`

用途：上傳梗圖圖片

>* 需先使用api : [txt store](https://github.com/ntub-109205/api/blob/master/POST%20txt_store.md)

* Parameters

|key  |type                |
|-----|--------------------|
|image|required;jpg;png;gif|

>* required為必要

---

* Return Values

```yaml
{"success":"your posts has been successfully saved!"}
```

---

* Examples (1)

上傳公開的梗圖

* execute [txt store](https://github.com/ntub-109205/api/blob/master/POST%20txt_store.md)

```html
http://140.131.115.99/api/txt/store

template_id = 1
share       = 1
tags        = #哈哈
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!"}
```

* then execute meme store api

```html
http://140.131.115.99/api/meme/store

image = 比讚貓咪2.jpg
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!"}
```

---

* Examples (2)

上傳公開的gif

* execute [txt store](https://github.com/ntub-109205/api/blob/master/POST%20txt_store.md)

```html
http://140.131.115.99/api/txt/store

share       = 1
tags        = #哈哈
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!"}
```

* then execute meme store api

```html
http://140.131.115.99/api/meme/store

image = 貓.gif
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!"}
```