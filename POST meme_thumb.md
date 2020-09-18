#### `<POST> http://140.131.115.99/api/meme/thumb`

用途：按讚(收回讚)梗圖

* Parameters

|key    |type            |
|-------|----------------|
|meme_id|required;meme_id|

>* required為必要
>* 若資料庫沒有該meme_id則會返回錯誤訊息

---

* Return Values

```yaml
{
    "thumb": ${boolean}
}
```

>* 回傳值為按讚後的狀態

---

* Examples (1)

對meme_id為1的梗圖按讚

```html
http://140.131.115.99/api/meme/thumb

meme_id = 1
```

* Above example will output

```yaml
{
    "thumb": "1"
}
```

---

* Examples (2)

收回meme_id為1的梗圖讚

```html
http://140.131.115.99/api/meme/thumb

meme_id = 1
```

* Above example will output

```yaml
{
    "thumb": "0"
}
```
