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

## Wiki 커맨드 강제 매핑

사용자가 wiki 관련 작업을 자연어로 요청할 때, 반드시 아래 툴/스킬을 사용해야 한다. 예외 없음.

| 사용자 발화 예시 | 반드시 사용할 툴/스킬 |
|---|---|
| "wiki에 추가해줘", "wiki에 넣어줘", "wiki 저장해줘" | `mcp__plugin_oh-my-claudecode_t__wiki_add` 툴 |
| "wiki 푸시해줘", "wiki 올려줘", "wiki 공유해줘" | `wiki-push` 스킬 (`Skill("wiki-push")`) |
| "wiki 풀해줘", "wiki 받아와", "최신 wiki 불러와" | `wiki-pull` 스킬 (`Skill("wiki-pull")`) |
| "wiki 검색해줘", "wiki에서 찾아줘" | `mcp__plugin_oh-my-claudecode_t__wiki_query` 툴 |
| "wiki 목록 보여줘", "wiki 리스트" | `mcp__plugin_oh-my-claudecode_t__wiki_list` 툴 |
| "wiki 읽어줘", "wiki 페이지 열어줘" | `mcp__plugin_oh-my-claudecode_t__wiki_read` 툴 |
| "wiki 정리해줘", "wiki lint" | `mcp__plugin_oh-my-claudecode_t__wiki_lint` 툴 |

자연어 표현이 위 예시와 정확히 일치하지 않아도, wiki 작업 의도가 명확하면 해당 툴/스킬을 반드시 사용한다.

## wiki 등록
`/wiki-add` 커맨드 사용 (아래 참고)

## 팀 동기화
- 다른 팀원 내용 받기: `git pull`
- 내 wiki 공유: `git push` (여러 개 추가 후 한 번에 가능)
