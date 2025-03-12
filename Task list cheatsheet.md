---
sticker: lucide//list-checks
---
All your tasks divided by categories

## ⌛ Pending / Scheduled Tasks

```dataview
Task
FROM "/"
WHERE !completed
GROUP BY file.link
```

## ✅ Completed Tasks only

```dataview
Task
FROM "/"
WHERE completed
GROUP BY file.link
```