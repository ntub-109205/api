#### `<GET> http://140.131.115.99/api/meme/show/{category_id}`

>* category_id值為1(梗圖)、2(長輩圖)、3(gif)

用途：顯示梗圖

* Parameters

|key |type             |
|----|-----------------|
|time|sometimes;boolean|

>* sometimes為選擇性加入參數

---

* Return Values

```yaml
{
    "meme": [
        {
            "meme_id": ${meme_id},
            "filelink": ${filelink},
            "author": ${author},
            "template_id": ${template_id},
            "template_share": ${template_share}
            "count": ${梗圖的讚數量},
            "thumb": ${使用者是否按讚},
            "created_at": ${timestamp},
            "tags": (array) ${tags}
        },
    ]
}
```

>* 其中template_share為0表示該模板不公開，1為公開
>* 前端需判斷是否能以此模板製作梗圖

---

* Examples (1)

取類型為meme的梗圖，以讚數排序

```html
http://140.131.115.99/api/meme/show/1
```

* Above example will output

```yaml
{
    "meme": [
        {
            "meme_id": 3,
            "filelink": "http://140.131.115.99/images/meme/meme/1600403228.jpeg",
            "author": "10836023",
            "template_id": 1,
            "template_share": 0,
            "count": 1,
            "thumb": 1,
            "created_at": "2020-09-18 12:27:08",
            "tags": [
                "好棒"
            ]
        },
        {
            "meme_id": 1,
            "filelink": "http://140.131.115.99/images/meme/meme/1600238555.jpeg",
            "author": "kevin",
            "template_id": 1,
            "template_share": 1,
            "count": 0,
            "thumb": 0,
            "created_at": "2020-09-16 14:42:35",
            "tags": [
                "哈"
            ]
        }
    ]
}
```

---

* Examples (2)

取類型為meme的梗圖，以時間排序

``` html
http://140.131.115.99/api/template/show/1?time=1
```

* Above example will output

```yaml
{
    "meme": [
        {
            "meme_id": 4,
            "filelink": "http://140.131.115.99/images/meme/meme/1600404158.jpeg",
            "author": "10836023",
            "template_id": 1,
            "template_share": 1,
            "count": 0,
            "thumb": 0,
            "created_at": "2020-09-18 12:42:38",
            "tags": [
                "haha"
            ]
        },
        {
            "meme_id": 3,
            "filelink": "http://140.131.115.99/images/meme/meme/1600403228.jpeg",
            "author": "10836023",
            "template_id": 1,
            "template_share": 0,
            "count": 1,
            "thumb": 1,
            "created_at": "2020-09-18 12:27:08",
            "tags": [
                "好棒"
            ]
        },
    ]
}
```
