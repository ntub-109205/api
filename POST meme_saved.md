#### `<POST> http://140.131.115.99/api/meme/saved`

用途：收藏(取消收藏)梗圖

* Parameters

|key    |type            |
|-------|----------------|
|meme_id|required;meme_id|

>* required為必要
>* 若資料庫沒有該meme_id則會返回錯誤訊息

---

* Return Values

```yaml
{"saved":${boolean}}
```

>* 回傳值為收藏後的狀態

---

* Examples (1)

收藏meme_id為1的模板

```html
http://140.131.115.99/api/meme/saved

meme_id = 1
```

* Above example will output

```yaml
{"saved":"1"}
```

---

* Examples (2)

取消收藏meme_id為1的模板

```html
http://140.131.115.99/api/meme/saved

meme_id = 1
```

* Above example will output

```yaml
{"saved":"0"}
```
