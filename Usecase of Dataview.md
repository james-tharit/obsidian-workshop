# Table
```dataview
table file.mtime as "last modified"
from "solar"
```
# Table for in-completed notes
```dataview
table file.mtime as "last modified"
WHERE status="incompleted"
SORT file.mtime DESC
```

# Table for tags
```dataview
TABLE WITHOUT ID Tag, map(rows, (r) => link(r.file.link, r.title)) AS Notes 
FROM "/"
FLATTEN file.tags as Tag 
GROUP BY Tag 
```
---

# List
```dataview
list file.mtime
from "solar"
```

# List for in-completed
```dataview
list file.mtime
from "solar"
WHERE status="incompleted"
```
---

# Task
```dataview
task FROM "solar"
```
