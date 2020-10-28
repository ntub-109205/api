#### `<GET> http://140.131.115.99/api/template/show/{category_id}`

>* category_id值為1(梗圖)或2(長輩圖)或0(全部)

用途：顯示模板

* Parameters

|key  |type             |
|-----|-----------------|
|time |sometimes;boolean|
|user |sometimes;boolean|
|limit|sometimes;numeric|

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
            "created_at": "2020-09-16 14:41:25"
        },
        {
            "id": 2,
            "filelink": "http://140.131.115.99/images/templates/meme/1600353008.jpeg",
            "name": "小貓",
            "author": "10836023",
            "count": 0,
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
            "created_at": "2020-09-17 22:30:08"
        },
        {
            "id": 1,
            "filelink": "http://140.131.115.99/images/templates/meme/1600238485.png",
            "name": "兇貓",
            "author": "kevin",
            "count": 1,
            "created_at": "2020-09-16 14:41:25"
        }
    ]
}
```

---

* Examples (3)

取類型為meme的模板，以時間排序，並只顯示自己所製做的模板

```html
http://140.131.115.99/api/template/show/1?time=1&user=1
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
            "created_at": "2020-09-16 14:41:25"
        }
    ]
}
```

---

* Examples (4)

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
            "created_at": "2020-10-28 18:31:39"
        },
        {
            "id": 2,
            "filelink": "http://140.131.115.99/images/templates/elder/1603881131.png",
            "name": "example elder",
            "author": "10836023",
            "count": 0,
            "created_at": "2020-10-28 18:32:11"
        }
    ]
}

--- 以下略 ---
```
