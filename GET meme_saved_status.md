#### `<GET> http://140.131.115.99/api/meme/saved/{meme_id}`

用途：顯示使用者是否有收藏此梗圖

---

* Return Values

```yaml
{"saved":"0"}
```

>* 0：沒收藏 
>* 1：有收藏

---

* Examples

顯示使用者是否有收藏meme_id為1的梗圖

```html
http://140.131.115.99/api/meme/saved/1
```

* Above example will output

```yaml
{"saved":"0"}
```

>* 代表該使用者沒有收藏meme_id為1的梗圖
