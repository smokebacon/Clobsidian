---
create: <% tp.file.creation_date() %>
tags:
  - dailynote
---
> [!error]+ Overdue
> ```dataview
> task
> FROM "Daily Notes"
> WHERE !fullyCompleted AND date(file.name) < date(today)
> GROUP BY (date(today) - date(file.name) + " ago")
> SORT rows.file.day ASC
> ```
>
> > [!example]+ Page tasks
> > ```dataview
> > task
> > FROM !"Daily Notes"
> > WHERE !fullyCompleted AND scheduled AND date(scheduled) < date(today)
> > GROUP BY (scheduled + " (" + (date(today) - date(scheduled) + " ago") + ")<br/> "+ file.link) AS summary
> > ```
> > ```dataview
> > task
> > FROM !"Daily Notes"
> > WHERE !fullyCompleted AND scheduled AND date(scheduled) = date(today)
> > GROUP BY (scheduled + " (Today)" + "<br/> "+ file.link) AS summary
> > ```

# <% tp.date.now("dddd DD MMM YY", 0, tp.file.title, "YYYY-MM-DD") %>

<% tp.file.cursor(1) %>



---


## ⌛ Scheduled for Later

> [!tldr]- Daily notes
> ```dataview
> task
> FROM "Daily Notes"
> WHERE !fullyCompleted AND date(file.name) > date(today)
> GROUP BY file.link + " (in " + ( date(file.name) - date(today) + ")" )
> SORT rows.file.day ASC
> ```

> [!cite]- Page Tasks
> ```dataview
> task
> FROM ""
> WHERE !fullyCompleted AND date(scheduled) > date(today)
> GROUP BY (scheduled + " (in " + (date(scheduled) - date(today)) + ")<br/> "+ file.link) AS summary
> ```

