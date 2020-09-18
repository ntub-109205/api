#### `<POST> http://140.131.115.99/api/txt/memeStore`

用途：上傳梗圖的文字訊息

>* 需搭配api : meme_store

* Parameters

|key        |type                |
|--------   |--------------------|
|template_id|required;template_id|
|meme_share |required;boolean    |
|tags       |sometimes;string    |

>* required為必要
>* 若資料庫沒有該template_id則會返回錯誤訊息
>* meme_share只能為0(非公開)或1(公開)
>* sometimes為選擇性加入參數
>* tags字串以#做分割

---

* Return Values

```yaml
{"success":"your posts has been successfully saved!"}
```

---

* Examples

```html
http://140.131.115.99/api/txt/memeStore

template_id = 1
meme_share  = 1
tags        = #好棒
```

* Above example will output

```yaml
{"success":"your posts has been successfully saved!"}
```