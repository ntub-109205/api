#### `<GET> http://140.131.115.99/api/profile/show/myWork`

用途：顯示該使用者製作的所有梗圖及模板

---

* Return Values

```yaml
{
    "meme": {
        "meme": {
            "count": ${使用者製作梗圖為${category}的數量},
            "meme_id": ${meme_id},
            "filelink": ${filelink},
            "template_id": ${template_id},
            "created_at": ${timestamp}
        }
    },
    "templates": {
        "meme": {
            "count": ${使用者製作模板為${category}的數量},
            "template_id": ${template_id},
            "filelink": ${filelink},
            "created_at": ${timestamp}
        }
    }
}
```

>* 以使用者製作時間排序

---

* Examples

```html
http://140.131.115.99/api/profile/show/myWork
```

* Above example will output

```yaml
{
    "meme": {
        "meme": {
            "count": 3,
            "meme_id": 4,
            "filelink": "http://140.131.115.99/images/meme/meme/1600404158.jpeg",
            "template_id": 1,
            "created_at": "2020-09-18 12:42:38"
        }
    },
    "templates": {
        "meme": {
            "count": 2,
            "template_id": 3,
            "filelink": "http://140.131.115.99/images/templates/meme/1600401481.jpeg",
            "created_at": "2020-09-18 11:58:01"
        }
    }
}
```

代表該使用者

>* 製作了3張類型為meme的梗圖，最近製作類型為meme的梗圖的id為4，filelink為1600404158.jpeg，使用template_id為1的模板製作
>* 製作了2張類型為meme的模板，最近製作類型為meme的模板的id為3，filelink為1600401481.jpeg
