#### `<POST> http://140.131.115.99/api/meme/store`

用途：上傳梗圖圖片

>* 需搭配api : meme_txt_store

* Parameters

|key       |type            |
|----------|----------------|
|meme_image|required;jpg;png|

>* required為必要

---

* Return Values

```yaml
{"success":"your posts has been successfully saved!"}
```

---

* Examples

```html
http://140.131.115.99/api/meme/store

meme_image = 比讚貓咪2.jpg
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!"}
```