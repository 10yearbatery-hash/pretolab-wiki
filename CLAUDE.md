# PRETO LABS 팀 Wiki

## 자동 로드
이 폴더에서 대화를 시작할 때마다:
1. `.omc/wiki/index.md` 를 읽어서 전체 wiki 목록 파악
2. 대화 흐름에 따라 관련 wiki 페이지 자동 참조
3. 사용자가 wiki를 언급하지 않아도 관련 내용 자동으로 반영해서 답변

## wiki 검색
"wiki에서 X 찾아줘" / "X 관련 내용 있어?" 요청 시:
→ `.omc/wiki/` 폴더 전체에서 키워드 검색 후 관련 파일 읽어서 요약

## wiki 읽기
"X wiki 보여줘" 요청 시:
→ `.omc/wiki/` 에서 해당 파일 찾아 전체 내용 표시

## wiki 등록
`/wiki-add` 커맨드 사용 (아래 참고)

## 팀 동기화
- 다른 팀원 내용 받기: `git pull`
- 내 wiki 공유: `git push` (여러 개 추가 후 한 번에 가능)
