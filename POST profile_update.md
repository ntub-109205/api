#### `<POST> http://140.131.115.99/api/profile/update`

用途：更改使用者作品基本設定

* Parameters

|key  |type                            |
|-----|--------------------------------|
|table|required;In('meme', 'templates')|
|id   |required;numeric                |
|field|required;In('share', 'name')    |
|value|required;bool<=>string          |

>* required為必要
>* table值只能為meme或templates
>* field以table值決定，若table為meme則只能為share；若table為templates則能為share或name
>* value型態以field值決定，若field為share，則為bool；若field為name，則為string
>* 只能更改自己的作品設定

以下將由範例詳細說明

---

* Return Values

```yaml
{
    "success": "This post was successfully change!"
}
```

---

* Examples (1)

設定meme_id = 2(需要為自己的作品)的梗圖為非公開

```html
http://140.131.115.99/api/profile/update

table = meme
id    = 2
field = share
value = 0
```

>* 0為非公開，1為公開

* Above example will output

```yaml
{
    "success": "This post was successfully change!"
}
```

* Verification

excute [meme show](https://github.com/ntub-109205/api/blob/master/GET%20meme_show.md)

```html
http://140.131.115.99/api/meme/show/1?user=1&time=1
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
            "template_share": 1,
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

>* meme_id = 2的梗圖meme_share更改為0(非公開)

---

* Examples (2)

設定template_id = 1(需要為自己的作品)的模板為非公開

```html
http://140.131.115.99/api/profile/update

table = templates
id    = 1
field = share
value = 0
```

>* 0為非公開，1為公開

* Above example will output

```yaml
{
    "success": "This post was successfully change!"
}
```

* Verification

excute [template show](https://github.com/ntub-109205/api/blob/master/GET%20template_show.md)

```html
http://140.131.115.99/api/template/show/1?user=1&time=1
```

* Above example will output

```yaml
{
    "templates": [
        {
            "id": 1,
            "filelink": "http://140.131.115.99/images/templates/meme/1604113246.png",
            "name": "example meme",
            "author": "kevin",
            "count": 1,
            "created_at": "2020-10-31 11:00:47",
            "share": 0
        }
    ]
}
```

>* template_id = 1的模板share更改為0(非公開)