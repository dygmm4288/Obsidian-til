## 끝
```dataview
table status as "상태", date as "날짜"
from "til"
where status = "done"
sort date desc
```
## 진행중
```dataview
table status as "상태", date as "날짜"
from "til"
where status = "in-progress"
sort date desc
```


