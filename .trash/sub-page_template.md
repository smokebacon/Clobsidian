---
id: <% tp.file.creation_date("YYYYMMDDHHmmss") %>
template: "[[sub-page_template]]"
aliases: []
tags:
---

<% tp.file.cursor(1) %>










---
## Related tasks

> [!error] Overdue]
> ```tasks
> description includes [[<% tp.file.title %>]]
> path does not include <% tp.file.title %>
> not done
> scheduled before today
> group by function (!task.happens.moment) ? '%%4%% Undated' : result = task.happens.moment.isSameOrBefore(moment(), 'day') ?'%%1%% ' + ("%%"+moment().subtract((isNaN(task.happens.moment.fromNow(true).split(" ")[0])?1:task.happens.moment.fromNow(true).split(" ")[0]),task.happens.moment.fromNow(true).split(" ")[1]).format("YYYYMMDD") + "%%" + task.happens.moment.fromNow()): result = task.happens.moment.isSame(moment(), 'day') ? '%%2%% Today' : '%%3%% ' + ("%%"+moment().add((isNaN(task.happens.moment.fromNow(true).split(" ")[0])?1:task.happens.moment.fromNow(true).split(" ")[0]),task.happens.moment.fromNow(true).split(" ")[1]).format("YYYYMMDD") + "%%" + task.happens.moment.fromNow())
> 
> hide done date
> hide scheduled date
> hide task count
> ```

> [!cite] Linked
> ```tasks
> not done
> scheduled after yesterday
> description includes [[<% tp.file.title %>]]
> path does not include <% tp.file.title %>
> group by function (!task.happens.moment) ? '%%4%% No date' : result = task.happens.moment.isSameOrBefore(moment(), 'day') ?'%%1%% ' + ("%%"+moment().subtract((isNaN(task.happens.moment.fromNow(true).split(" ")[0])?1:task.happens.moment.fromNow(true).split(" ")[0]),task.happens.moment.fromNow(true).split(" ")[1]).format("YYYYMMDD") + "%%" + task.happens.moment.fromNow()): result = task.happens.moment.isSame(moment(), 'day') ? '%%2%% Today' : '%%3%% ' + ("%%"+moment().add((isNaN(task.happens.moment.fromNow(true).split(" ")[0])?1:task.happens.moment.fromNow(true).split(" ")[0]),task.happens.moment.fromNow(true).split(" ")[1]).format("YYYYMMDD") + "%%" + task.happens.moment.fromNow())
> hide done date
> hide scheduled date
> hide task count
> ```

> [!done] Archive
> ```tasks
> done
> description includes [[<% tp.file.title %>]]
> path does not include <% tp.file.title %>
> group by function (!task.done.moment) ? '%%4%% No Date' : result = task.done.moment.isSameOrBefore(moment(), 'day') ?'%%1%% ' + ("%%"+moment().subtract((isNaN(task.done.moment.fromNow(true).split(" ")[0])?1:task.done.moment.fromNow(true).split(" ")[0]),task.done.moment.fromNow(true).split(" ")[1]).format("YYYYMMDD") + "%%" + task.done.moment.fromNow()): result = task.happens.done.isSame(moment(), 'day') ? '%%2%% Today' : '%%3%% ' + ("%%"+moment().add((isNaN(task.done.moment.fromNow(true).split(" ")[0])?1:task.happens.done.fromNow(true).split(" ")[0]),task.happens.done.fromNow(true).split(" ")[1]).format("YYYYMMDD") + "%%" + task.done.moment.fromNow())
> sort by filename reversed
> hide done date
> hide scheduled date
> hide task count
> ```