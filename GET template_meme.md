#### `<GET> http://140.131.115.99/api/template/meme/{template_id}`

用途：顯示引用此模板所製作的梗圖

* Parameters

|key    |type             |
|-------|-----------------|
|exclude|sometimes;meme_id|

>* sometimes為選擇性加入參數

---

* Return Values

```yaml
{
    "meme": [
        {
            "id": ${meme_id},
            "filelink": ${filelink},
            "author": ${author},
            "count": ${梗圖的讚數量},
            "thumb": ${使用者是否按讚},
            "tags": (array) ${tags},
        },
    ]
}
```

---

* Examples (1)

顯示引用template_id為1的模板所製作的所有梗圖

```html
http://140.131.115.99/api/template/meme/1
```

* Above example will output

```yaml
{
    "meme": [
        {
            "id": 1,
            "filelink": "http://140.131.115.99/images/meme/meme/1600238555.jpeg",
            "author": "kevin",
            "count": 0,
            "thumb": 0,
            "tags": [
                "哈"
            ]
        },
        {
            "id": 2,
            "filelink": "http://140.131.115.99/images/meme/meme/1600357902.jpeg",
            "author": "10836023",
            "count": 0,
            "thumb": 0,
            "tags": [
                "好棒"
            ]
        }
    ]
}
```

---

* Examples (2)

顯示引用template_id為1的模板所製作的所有梗圖，但不包含meme_id為1的梗圖

```html
http://140.131.115.99/api/template/meme/1?exclude=1
```

* Above example will output

```yaml
{
    "meme": [
        {
            "id": 2,
            "filelink": "http://140.131.115.99/images/meme/meme/1600357902.jpeg",
            "author": "10836023",
            "count": 0,
            "thumb": 0,
            "tags": [
                "好棒"
            ]
        }
    ]
}
```