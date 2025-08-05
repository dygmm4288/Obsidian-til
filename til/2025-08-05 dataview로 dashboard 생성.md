---
title: 2025-08-05 dataview로 dashboard 생성
date: 2025-08-05
status: in-progress
---
## 배운 것
 - sql을 통해서 dataview를 만들 수 있다.
 - from절에는 폴더 이름을 넣으면 되고 dquote 사용해야 한다.
 ```
table date as "날짜", status as "상태"
from "til"
sort date desc
```

## 다음 할 일
-  dataview where절 추가