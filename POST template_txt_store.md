#### `<POST> http://140.131.115.99/api/txt/templateStore`

用途：上傳模板的文字訊息
>* 需搭配api : template_store

* Parameters

|key        |type                   |
|--------   |-----------------------|
|category_id|required;In(['1', '2'])|
|name       |required;string        |
|share      |required;boolean       |

>* required為必要
>* category_id值只能為1(梗圖)或2(長輩圖)
>* share為boolean，0為非公開;1為公開

---

* Return Values

```yaml
{"success":"your posts has been successfully saved!"}
```

---

* Examples

```html
http://140.131.115.99/api/txt/templateStore

category_id = 1
name        = kevin
share       = 1
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!"}
```