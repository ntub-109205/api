#### `<GET> http://140.131.115.99/api/tag`

用途：顯示熱門 tags

* Parameters

|key  |type             |
|-----|-----------------|
|limit|sometimes;numeric|

>* sometimes為選擇性加入參數

---

* Return Values

```yaml
{
    "popular": [
        {
            "tag_id": ${tag_id},
            "name": ${tag_name},
        }
    ]
}
```

---

* Examples (1)

取所有的tags，以梗圖引用次數排序(多->少)

```html
http://140.131.115.99/api/tag
```

* Above example will output

```yaml
{
    "popular": [
        {
            "tag_id": 1,
            "name": "哈哈"
        },
        {
            "tag_id": 2,
            "name": "好棒"
        }
    ]
}
```

---

* Examples (2)

取"前十筆"的tags，以梗圖引用次數排序(多->少)

```html
http://140.131.115.99/api/tag?limit=10
```

* Above example will output

```yaml
{
    "popular": [
        {
            "tag_id": 1,
            "name": "哈哈"
        },
        {
            "tag_id": 2,
            "name": "好棒"
        }
    ]
}

--- 以下略 ---
```
