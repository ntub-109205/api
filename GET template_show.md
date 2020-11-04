#### `<GET> http://140.131.115.99/api/template/show/{category_id}`

>* category_id值為1(梗圖)或2(長輩圖)或0(全部)

用途：顯示模板

* Parameters

|key     |type                           |
|--------|-------------------------------|
|time    |sometimes;boolean              |
|profile |sometimes;In('saved', 'myWork')|
|limit   |sometimes;numeric              |
|name    |sometimes;string               |

>* sometimes為選擇性加入參數

---

* Return Values

```yaml
{
    "templates": [
        {
            "id": ${template_id},
            "filelink": ${filelink},
            "name": ${template_name},
            "author": ${author},
            "count": ${模板被引用次數},
            "share": ${share},
            "created_at": "2020-09-16 14:41:25"
        }
    ]
}
```

---

* Examples (1)

取類型為meme的模板，以引用次數排序

```html
http://140.131.115.99/api/template/show/1
```

* Above example will output

```yaml
{
    "templates": [
        {
            "id": 1,
            "filelink": "http://140.131.115.99/images/templates/meme/1600238485.png",
            "name": "兇貓",
            "author": "kevin",
            "count": 1,
            "share": 1,
            "created_at": "2020-09-16 14:41:25"
        },
        {
            "id": 2,
            "filelink": "http://140.131.115.99/images/templates/meme/1600353008.jpeg",
            "name": "小貓",
            "author": "10836023",
            "count": 0,
            "share": 1,
            "created_at": "2020-09-17 22:30:08"
        }
    ]
}
```

---

* Examples (2)

取類型為meme的模板，以時間排序

``` html
http://140.131.115.99/api/template/show/1?time=1
```

* Above example will output

```yaml
{
    "templates": [
        {
            "id": 2,
            "filelink": "http://140.131.115.99/images/templates/meme/1600353008.jpeg",
            "name": "小貓",
            "author": "10836023",
            "count": 0,
            "share": 1,
            "created_at": "2020-09-17 22:30:08"
        },
        {
            "id": 1,
            "filelink": "http://140.131.115.99/images/templates/meme/1600238485.png",
            "name": "兇貓",
            "author": "kevin",
            "count": 1,
            "share": 1,
            "created_at": "2020-09-16 14:41:25"
        }
    ]
}
```

---

* Examples (3)

取類型為meme的模板，以時間排序，並只顯示自己所"製做"的模板

```html
http://140.131.115.99/api/template/show/1?time=1&profile=myWork
```

* Above example will output

```yaml
{
    "templates": [
        {
            "id": 1,
            "filelink": "http://140.131.115.99/images/templates/meme/1600238485.png",
            "name": "兇貓",
            "author": "kevin",
            "count": 1,
            "share": 1,
            "created_at": "2020-09-16 14:41:25"
        }
    ]
}
```

---

* Examples (4)

取類型為meme的模板，以時間排序，並只顯示自己所"收藏"的"公開"模板

```html
http://140.131.115.99/api/template/show/1?time=1&profile=saved
```

* Above example will output

```yaml
{
    "templates": [
        {
            "id": 2,
            "filelink": "http://140.131.115.99/images/templates/meme/1604481524.png",
            "name": "example template meme",
            "author": "test",
            "count": 0,
            "share": 1,
            "created_at": "2020-11-04 17:18:44"
        },
        {
            "id": 1,
            "filelink": "http://140.131.115.99/images/templates/meme/1604481375.png",
            "name": "example meme",
            "author": "test",
            "count": 1,
            "share": 1,
            "created_at": "2020-11-04 17:16:15"
        }
    ]
}
```

>* 代表該使用者收藏了template_id為1跟2的模板

---

* Examples (5)

取"前十筆"模板，以引用次數排序

```html
http://140.131.115.99/api/template/show/0?limit=10
```

* Above example will output

```yaml
{
    "templates": [
        {
            "id": 1,
            "filelink": "http://140.131.115.99/images/templates/meme/1603881099.png",
            "name": "example",
            "author": "10836023",
            "count": 1,
            "share": 1,
            "created_at": "2020-10-28 18:31:39"
        },
        {
            "id": 2,
            "filelink": "http://140.131.115.99/images/templates/elder/1603881131.png",
            "name": "example elder",
            "author": "10836023",
            "count": 0,
            "share": 1,
            "created_at": "2020-10-28 18:32:11"
        }
    ]
}

--- 以下略 ---
```

---

* Examples (6)

取name為"example"的模板，以引用次數排序

>* 後端會將example前後加上萬用字元，也就是搜尋出的結果為%example%

```html
http://140.131.115.99/api/template/show/0?name=example
```

* Above example will output

```yaml
{
    "templates": [
        {
            "id": 1,
            "filelink": "http://140.131.115.99/images/templates/meme/1604481375.png",
            "name": "example meme",
            "author": "test",
            "count": 1,
            "share": 1,
            "created_at": "2020-11-04 17:16:15",
        },
        {
            "id": 2,
            "filelink": "http://140.131.115.99/images/templates/meme/1604481524.png",
            "name": "example template meme",
            "author": "test",
            "count": 0,
            "share": 1,
            "created_at": "2020-11-04 17:18:44"
        }
    ]
}
```

---

* Examples (7)

取name為"example"的模板，以引用次數排序，且只取"前十筆"

```html
http://140.131.115.99/api/template/show/0?name=example&limit=10
```

* Above example will output

```yaml
{
    "templates": [
        {
            "id": 1,
            "filelink": "http://140.131.115.99/images/templates/meme/1604481375.png",
            "name": "example meme",
            "author": "test",
            "count": 1,
            "share": 1,
            "created_at": "2020-11-04 17:16:15"
        },
        {
            "id": 2,
            "filelink": "http://140.131.115.99/images/templates/meme/1604481524.png",
            "name": "example template meme",
            "author": "test",
            "count": 0,
            "share": 1,
            "created_at": "2020-11-04 17:18:44"
        }
    ]
}
```
