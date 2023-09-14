---
sticker: lucide//list
---

# ⌛ Pending / Scheduled Tasks

```dataview
Task
FROM "/"
WHERE !completed
GROUP BY file.link
```

# ✅ Completed tasks only
```dataview
Task
FROM "/"
WHERE completed
GROUP BY file.link
```