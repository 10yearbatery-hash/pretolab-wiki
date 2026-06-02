# PRETO LABS 팀 Wiki

## 자동 로드
이 폴더에서 대화를 시작할 때마다:
1. `.omc/wiki/index.md` 를 읽어서 전체 wiki 목록 파악
2. 대화 흐름에 따라 관련 wiki 페이지 자동 참조
3. 사용자가 wiki를 언급하지 않아도 관련 내용 자동으로 반영해서 답변

## wiki 추가 (강제 커맨드 발동)

"wiki에 추가해줘", "wiki에 넣어줘", "wiki 저장해줘" 등 **추가 의도가 담긴 모든 자연어 발화**는 예외 없이 `/wiki-add` 커맨드를 실행한다.

- CLAUDE.md에서 직접 파일을 만들지 말 것
- 표현이 위 예시와 정확히 일치하지 않아도, 추가 의도가 명확하면 무조건 커맨드를 발동
- 실제 로직은 `.claude/commands/wiki-add.md` 에만 정의됨

## wiki 검색
"wiki에서 X 찾아줘" / "X 관련 내용 있어?" / "wiki 검색해줘" 요청 시:
→ `.omc/wiki/` 폴더 전체에서 키워드로 파일 내용 검색 후 관련 파일 읽어서 요약

## wiki 목록
"wiki 목록 보여줘", "wiki 리스트" 요청 시:
→ `.omc/wiki/index.md` 파일을 읽어서 전체 목록 표시

## wiki 읽기
"X wiki 보여줘", "wiki 읽어줘", "wiki 페이지 열어줘" 요청 시:
→ `.omc/wiki/index.md` 에서 해당 파일명 찾은 뒤, 해당 `.omc/wiki/{파일}` 전체 내용 표시

## wiki 삭제
"wiki 삭제해줘", "wiki 지워줘" 요청 시:
→ 해당 `.omc/wiki/{파일}` 삭제 후, `index.md` 에서 해당 항목 제거, 페이지 카운트 -1

## wiki 정리 / lint
"wiki 정리해줘", "wiki lint", "wiki 클린" 등 정리·점검 의도가 담긴 요청 시:
→ `/wiki-clean` 커맨드를 실행한다.

## 팀 동기화
- 다른 팀원 내용 받기: `/wiki-pull` 커맨드
- 내 wiki 공유: `/wiki-push` 커맨드
