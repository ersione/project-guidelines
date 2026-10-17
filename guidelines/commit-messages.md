# 커밋 메시지

Conventional Commits 형식을 사용하고 최종 변경의 목적을 설명합니다.

```text
type(scope): subject

What changed and why, when a body is useful.

Refs #123
```

## 타입과 범위

| 타입 | 의미 |
|---|---|
| `feat` | 새 기능 |
| `fix` | 버그 수정 |
| `docs` | 문서 변경 |
| `style` | 동작을 바꾸지 않는 서식 정리 |
| `refactor` | 동작을 유지하는 구조 개선 |
| `test` | 테스트 추가·수정 |
| `chore` | 빌드·도구·설정·의존성 관리 |
| `perf` | 성능 개선 |

`scope`는 선택 사항이며 `api`, `auth`, `readme`처럼 변경 영역을 나타냅니다.

## 제목과 본문

- 제목은 50자 이내를 권장하고 72자를 넘기지 않습니다. 끝에 마침표를 붙이지 않습니다.
- 기본 제목은 짧은 영문 명령형으로 씁니다. 프로젝트가 한국어 등 다른 언어를 지정하면 따릅니다.
- 코드 목록보다 무엇이 왜 달라지는지 설명합니다. 작은 변경은 제목만으로 충분합니다.
- 본문은 필요한 경우에만 쓰고 제목과 빈 줄로 구분하며 72자 안팎에서 줄바꿈합니다.
- 관련 티켓·이슈가 실제로 있을 때만 footer에 `Refs`, `Fixes`, `Closes`를 씁니다. 자동 종료를 의도할 때만 `Fixes`·`Closes`를 사용합니다.
- 호환성을 깨는 변경은 타입·범위 뒤에 `!`를 붙이고 `BREAKING CHANGE:`로 영향과 필요한 대응을 설명합니다.
- 비밀값·개인 경로·개인정보·작업 중 메모·임시 `WIP` 메시지를 넣지 않습니다. 공동 작성자는 실제 기여와 확인된 신원만 표기합니다.

## 예시

```text
docs(readme): add architecture overview
```

```text
fix(auth): prevent repeated token refresh

Reuse an in-flight refresh so concurrent requests do not
invalidate each other's credentials.
```

```text
refactor(api)!: rename message cursor field

BREAKING CHANGE: Use next_cursor instead of cursor in clients.
```

에디터에서 사용할 양식은 [커밋 템플릿](../templates/commit-message.txt)에 있습니다. 브랜치 접두사와 커밋 타입은 별개이므로 `feature/` 브랜치에서 `feat` 커밋을 사용할 수 있습니다.
