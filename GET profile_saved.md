#### `<GET> http://140.131.115.99/api/profile/show/saved`

用途：顯示該使用者收藏的所有梗圖及模板

---

* Return Values

```yaml
{
    "meme": {
        ${category}: {
            "count": ${使用者收藏梗圖為${category}的數量},
            "id": ${meme_id},
            "filelink": ${filelink}
        }
    },
    "templates": {
        ${category}: {
            "count": ${使用者收藏模板為${category}的數量},
            "id": ${template_id},
            "filelink": ${filelink}
        }
    }
}
```

>* 以使用者收藏時間排序

---

* Examples

```html
http://140.131.115.99/api/profile/show/saved
```

* Above example will output

```yaml
{
    "meme": {
        "meme": {
            "count": 1,
            "id": 1,
            "filelink": "http://140.131.115.99/images/meme/meme/1600238555.jpeg"
        }
    },
    "templates": {
        "meme": {
            "count": 1,
            "id": 1,
            "filelink": "http://140.131.115.99/images/templates/meme/1600238485.png"
        }
    }
}
```

代表該使用者

>* 收藏了1張類型為meme的梗圖，最近收藏類型為meme的梗圖的id為1，filelink為1600238555.jpeg
>* 收藏了1張類型為meme的模板，最近收藏類型為meme的模板的id為1，filelink為1600238485.jpeg
