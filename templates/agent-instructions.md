# 공통 지침 연결 예시

아래 항목 중 필요한 것을 기존 에이전트 지침에 병합합니다. 원문을 복제하지 않고 해당 작업 전에 문서를 읽도록 명시합니다. 사용자 요청과 프로젝트별 명시적 규칙을 공통 기본값보다 우선합니다.

```markdown
## 공통 문서·Git 지침

- README를 작성·수정·검토하기 전에 https://github.com/ersione/project-guidelines/blob/main/guidelines/readme.md 를 읽고 따른다.
- 브랜치 생성 전 https://github.com/ersione/project-guidelines/blob/main/guidelines/git-workflow.md 를 읽고 작업 종류에 맞는 접두사를 사용한다. 사용자가 지정한 정확한 이름을 우선한다.
- 커밋 작성 전 https://github.com/ersione/project-guidelines/blob/main/guidelines/commit-messages.md 를 읽는다.
- PR 작성·수정 전 https://github.com/ersione/project-guidelines/blob/main/guidelines/pull-requests.md 를 읽는다.
- 코드 리뷰 시 https://github.com/ersione/project-guidelines/blob/main/guidelines/code-review.md 를 참고한다.
- 로컬 체크아웃이 있다면 같은 문서를 로컬에서 읽어도 된다. 접근하지 못한 원문을 읽은 것처럼 처리하지 않는다.
- 공통 규칙을 프로젝트별 문서로 복제하지 않는다. 프로젝트별 지침 파일은 명시적으로 요청받은 경우에만 추가한다.
```

Codex 사용자는 전역 `~/.codex/AGENTS.md`에 연결하거나, 프로젝트별 지침이 명시적으로 필요한 경우 해당 `AGENTS.md`에 추가할 수 있습니다. 전역과 프로젝트 지침은 함께 적용되며 범위와 우선순위를 고려해야 합니다. [공식 AGENTS.md 안내](https://learn.chatgpt.com/docs/agent-configuration/agents-md)

다른 에이전트는 그 도구가 실제로 읽는 지침 파일에 연결합니다. 링크 등록 자체가 모든 도구에서 원격 문서 자동 로딩을 보장하지는 않습니다.
