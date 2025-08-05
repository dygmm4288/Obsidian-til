---
title: "2025-08-05 dataview where절 세팅"
date: "2025-08-05"
status: in-progress
---

## 배운 것
- Data: dataview는 markdown frontmatter와 Inline fields에서 정보를 가져와서 볼트에서 데이터를 생성한다.
	- markdown frontmatter: 마크다운 문서 상단에 ---로 묶인 임의의 YAML로, 해당 문서에 대한 메타 데이터를 저장할 수 있다.
	- Inline Fields: 데이터뷰 기능으로 마크다운 문서에서 KEY::VALUE 문법을 사용한다.
- Where 절 사용
```
LIST
where due and due. date(today)

TASK
WHERE !completed

TABLE status as "상태"
from 'til'
where status = 'done'
```
## 다음 할 일
- 