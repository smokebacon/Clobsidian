---
create: <% tp.file.creation_date("YYYYMMDDHHmmss") %>
tags:
  - dailynote
---

## <% tp.date.now("dddd DD MMM YY", 0, tp.file.title, "YYYY-MM-DD") %>

<% tp.file.cursor(1) %>



---

> [!error]+ Overdue 
> ```dataview
> task
> FROM "Daily Notes"
> WHERE !fullyCompleted AND date(file.name) < date(today)
> GROUP BY (date(today) - date(file.name) + " ago")
> SORT rows.file.day ASC
> ```

> [!cite]+ Page tasks
> ```dataview
> task
> FROM !"Daily Notes"
> WHERE !fullyCompleted AND scheduled AND date(scheduled) = date(today)
> GROUP BY "Today"
> ```
> ```dataview
> task
> FROM !"Daily Notes"
> WHERE !fullyCompleted AND scheduled AND date(scheduled) < date(today)
> GROUP BY (scheduled + " (" + (date(today) - date(scheduled) + " ago") + ")<br/> "+ file.link + " " ) AS summary
> ```
