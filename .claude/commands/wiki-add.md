현재 대화 내용을 팀 wiki에 등록합니다.

다음 순서로 실행:

1. 현재 대화의 핵심 내용 정리 (불필요한 내용 제거)

2. 아래 형식으로 `.omc/wiki/{YYYY-MM-DD}-{슬러그}-{작성자}.md` 파일 생성:

```
---
title: 제목
category: reference | decision | pattern | session-log
tags: [태그1, 태그2]
date: YYYY-MM-DD
author: 작성자이름
---

# 제목

내용...
```

category 기준:
- `reference`: 시장조사, 인터뷰, 분석 자료
- `decision`: 팀이 내린 결정사항
- `pattern`: 반복 사용할 방법론/가이드
- `session-log`: 회의록, 작업 기록

3. 파일 생성 완료 후 안내:
"✅ wiki 등록 완료: {파일명}
팀과 공유하려면: git add .omc/wiki/ && git commit -m 'wiki: {제목}' && git push"
