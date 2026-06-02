현재 대화 내용을 팀 wiki에 등록합니다. OMC 없이도 동작합니다.

다음 순서로 실행:

## 1. 핵심 내용 정리

현재 대화에서 불필요한 부분을 제거하고 핵심 내용만 추출한다.

## 2. 메타데이터 결정

- **title**: 내용을 잘 설명하는 제목
- **tags**: 관련 키워드 배열 (예: ["인터뷰", "시장조사"])
- **category**: 아래 기준으로 선택
  - `reference`: 시장조사, 인터뷰, 분석 자료
  - `decision`: 팀이 내린 결정사항
  - `pattern`: 반복 사용할 방법론/가이드
  - `session-log`: 회의록, 작업 기록
  - `architecture`: 시스템/구조 설계
  - `debugging`: 버그 원인 및 해결
  - `environment`: 환경 설정, 인프라
  - `convention`: 코딩 컨벤션, 팀 규칙
- **slug**: title을 소문자+하이픈으로 변환 (예: "0601 회의록" → `0601-회의록`)
- **filename**: `{slug}.md`
- **now**: 현재 ISO 8601 시각 (예: `2026-06-02T09:00:00.000Z`)

## 3. wiki 파일 생성

`.omc/wiki/{filename}` 파일을 아래 형식으로 생성:

```
---
title: "{title}"
tags: {tags}
created: {now}
updated: {now}
sources: []
links: []
category: {category}
confidence: high
schemaVersion: 1
---

# {title}

{정리된 핵심 내용}
```

## 4. index.md 갱신

`.omc/wiki/index.md` 를 읽고, 해당 category 섹션에 아래 줄을 추가:

```
- [{title}]({filename}) — # {title}
```

- 해당 category 섹션이 없으면 새로 만든다.
- 파일 상단의 `> N pages` 카운트를 +1 증가시킨다.
- `Last updated:` 를 현재 시각으로 갱신한다.

## 5. log.md 기록

`.omc/wiki/log.md` 맨 아래에 아래 내용을 추가:

```
## [{now}] add
- **Pages:** {filename}
- **Summary:** Created new page "{title}"
```

## 6. 완료 안내

```
✅ wiki 등록 완료: {filename}
팀과 공유하려면: /wiki-push
```
