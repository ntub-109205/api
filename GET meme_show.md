#### `<GET> http://140.131.115.99/api/meme/show/{category_id}`

>* category_id值為1(梗圖)、2(長輩圖)、3(gif)

用途：顯示梗圖

* Parameters

|key     |type                           |
|--------|-------------------------------|
|time    |sometimes;boolean              |
|profile |sometimes;In('saved', 'myWork')|
|tag_name|sometimes;string               |

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
            "meme_share": ${meme_share}
            "count": ${梗圖的讚數量},
            "thumb": ${使用者是否按讚},
            "created_at": ${timestamp},
            "tags": (array) ${tags}
        },
    ]
}
```

>* 其中template_share為0表示該模板不公開，1為公開；meme_share為0表示該梗圖不公開，1為公開
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
            "meme_share": 1,
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
            "meme_share": 1,
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
            "meme_share": 1,
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
            "meme_share": 1,
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

---

* Examples (3)

取類型為meme的梗圖，以時間排序，並只顯示自己所"製做"的梗圖

``` html
http://140.131.115.99/api/meme/show/1?profile=myWork&time=1
```

* Above example will output

```yaml
{
    "meme": [
        {
            "meme_id": 2,
            "filelink": "http://140.131.115.99/images/meme/meme/1604113395.jpeg",
            "author": "kevin",
            "template_id": 1,
            "template_share": 0,
            "meme_share": 0,
            "count": 0,
            "thumb": 0,
            "created_at": "2020-10-31 11:03:15",
            "tags": [
                "bird"
            ]
        }
    ]
}
```

---

* Examples (4)

取類型為meme的梗圖，以時間排序，並只顯示自己所"收藏"的"公開"梗圖

``` html
http://140.131.115.99/api/meme/show/1?profile=saved&time=1
```

* Above example will output

```yaml
{
    "meme": [
        {
            "meme_id": 1,
            "filelink": "http://140.131.115.99/images/meme/meme/1604481669.jpeg",
            "author": "test",
            "template_id": 1,
            "template_share": 1,
            "meme_share": 1,
            "count": 1,
            "thumb": 1,
            "created_at": "2020-11-04 17:21:09",
            "tags": [
                "test meme"
            ]
        }
    ]
}
```

>* 代表該使用者收藏了meme_id為1的梗圖

若該使用者沒有收藏任何梗圖，則回傳key為meme的空陣列

```yaml
{
    "meme":[]
}
```

---

* Examples (5)

取類型為meme，tag為"made"的"公開"梗圖，以讚數排序

>* 後端會將made前後加上萬用字元，也就是搜尋出的結果為%made%

``` html
http://140.131.115.99/api/meme/show/1?tag_name=made
```

* Above example will output

```yaml
{
    "meme": [
        {
            "meme_id": 2,
            "filelink": "http://140.131.115.99/images/meme/meme/1604483150.jpeg",
            "author": "test",
            "template_id": 1,
            "template_share": 1,
            "meme_share": 1,
            "count": 0,
            "thumb": 0,
            "created_at": "2020-11-04 17:45:50",
            "tags": [
                "test made meme"
            ]
        }
    ]
}
```
