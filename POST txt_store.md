#### `<POST> http://140.131.115.99/api/txt/store`

用途：上傳文字訊息

* Parameters (1)

上傳模板的文字訊息

|key        |type                   |
|-----------|-----------------------|
|category_id|required;In(['1', '2'])|
|name       |required;max:255       |
|share      |required;boolean       |

>* required為必要
>* category_id只能為1(梗圖模板)或2(長輩圖模板)
>* share只能為0(非公開)或1(公開)

* Parameters (2)

上傳梗圖、長輩圖的文字訊息

|key        |type                |
|-----------|--------------------|
|template_id|required;template_id|
|share      |required;boolean    |
|tags       |sometimes;string    |

>* 若資料庫無此template_id則回傳錯誤訊息
>* tags字串以#做分割
>* sometimes為選擇性加入參數

* Parameters (3)

上傳gif的文字訊息

|key        |type                |
|-----------|--------------------|
|share      |required;boolean    |
|tags       |sometimes;string    |

---

* Return Values

```yaml
{"success":"your posts has been successfully saved!"}
```

---

* Examples (1)

上傳公開的梗圖模板

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

* then excute [template store](https://github.com/ntub-109205/api/blob/master/POST%20template_store.md)

```html
http://140.131.115.99/api/template/store

image = 鸚鵡.png
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!","template_id":1}
```

---

* Examples (2)

上傳公開的梗圖

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

* then excute [meme store](https://github.com/ntub-109205/api/blob/master/POST%20meme_store.md)

```html
http://140.131.115.99/api/meme/store

image = 比讚貓咪2.jpg
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!"}
```

---

* Examples (3)

上傳公開的gif

```html
http://140.131.115.99/api/txt/store

share       = 1
tags        = #哈哈
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!"}
```

* then excute [meme store](https://github.com/ntub-109205/api/blob/master/POST%20meme_store.md)

```html
http://140.131.115.99/api/meme/store

image = 貓.gif
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!"}
```