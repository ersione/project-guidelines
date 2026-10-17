# project-guidelines

프로젝트 README, 브랜치, 커밋, Pull Request와 릴리스 문서를 일관되게 작성하기 위한 공통 지침과 템플릿입니다.

[공통 지침](#공통-지침) · [템플릿](#템플릿) · [사용법](#사용법) · [기여 안내](CONTRIBUTING.md)

## 주요 기능

- 공개용 README 작성 기준과 아키텍처를 포함한 기본 양식
- 브랜치 이름·Conventional Commits·PR 제목과 본문 작성 규칙
- 변경의 목적·검증 근거를 확인하는 코드 리뷰 기준
- 복사해서 사용할 PR·버그 보고·기능 요청·릴리스 노트·변경 이력 양식
- 규칙 본문을 복제하지 않고 원문으로 연결하는 에이전트 지침 예시

## 공통 지침

| 문서 | 내용 |
|---|---|
| [README 작성](guidelines/readme.md) | 소개·기능·설치·사용법, 공개 범위와 아키텍처 위치 기준 |
| [Git 작업 흐름](guidelines/git-workflow.md) | 브랜치 이름, 작업 시작·커밋·푸시·PR·머지의 경계 |
| [커밋 메시지](guidelines/commit-messages.md) | 타입·범위·제목·본문·관련 이슈 형식 |
| [PR 작성](guidelines/pull-requests.md) | 문제와 결과를 먼저 설명하고 실제 검증을 기록하는 방법 |
| [코드 리뷰](guidelines/code-review.md) | 동작·회귀·보안·문서 검토와 피드백 기준 |
| [릴리스 문서](guidelines/releases.md) | 출시 상태·사용자 영향·호환성 안내와 버전별 변경 이력 |

## 템플릿

| 파일 | 적용 위치 |
|---|---|
| [README 기본형](templates/README.md) | 대상 프로젝트의 `README.md` |
| [커밋 메시지](templates/commit-message.txt) | Git의 저장소별 `commit.template` 설정 |
| [PR 본문](.github/pull_request_template.md) | 대상 프로젝트의 `.github/pull_request_template.md` |
| [버그 보고](.github/ISSUE_TEMPLATE/bug_report.md) | 대상 프로젝트의 `.github/ISSUE_TEMPLATE/` |
| [기능 요청](.github/ISSUE_TEMPLATE/feature_request.md) | 대상 프로젝트의 `.github/ISSUE_TEMPLATE/` |
| [릴리스 노트](templates/RELEASE_NOTES.md) | 버전별 초안 또는 GitHub Release 본문 |
| [변경 이력](templates/CHANGELOG.md) | 대상 프로젝트의 `CHANGELOG.md` |
| [에이전트 지침 연결 예시](templates/agent-instructions.md) | 사용 중인 전역 또는 프로젝트 지침에 필요한 링크만 반영 |

템플릿의 빈칸·예시·선택 항목은 실제 프로젝트에 맞게 수정합니다. 존재하지 않는 기능·명령·서비스 링크·CI 상태·라이선스를 만들지 않습니다. 기존 파일은 덮어쓰지 말고 필요한 내용을 병합하세요.

## 사용법

### 지침을 링크로 연결하기

사람과 에이전트가 해당 작업을 시작할 때 관련 원문을 읽도록 지시합니다. 링크를 적는 것만으로 모든 도구가 링크 내용을 자동으로 읽는 것은 아닙니다.

```markdown
- README 작성·수정·검토 전 https://github.com/ersione/project-guidelines/blob/main/guidelines/readme.md 를 읽고 따른다.
- 브랜치 생성 전 https://github.com/ersione/project-guidelines/blob/main/guidelines/git-workflow.md 를 읽는다.
- 커밋과 PR 작성 시 같은 저장소의 commit-messages.md와 pull-requests.md를 읽는다.
- 릴리스 노트·변경 이력 작성 시 같은 저장소의 releases.md를 읽는다.
- 사용자 요청과 프로젝트별 명시적 규칙이 공통 기본값보다 우선한다.
```

전체 연결 예시는 [에이전트 지침 템플릿](templates/agent-instructions.md)을 참고하세요. 전역 지침을 사용하는 환경에서는 각 프로젝트에 같은 규칙을 복제할 필요가 없습니다. 프로젝트별 지침 파일은 필요하고 명시적으로 요청된 경우에만 추가합니다.

### 필요한 양식 복사하기

저장소를 내려받습니다.

```sh
git clone https://github.com/ersione/project-guidelines.git
```

다음 명령은 **적용할 프로젝트의 루트**에서 실행합니다. 변수에는 위 저장소를 체크아웃한 경로를 지정합니다. 예시는 기존 파일이 있으면 복사하지 않습니다.

```sh
GUIDELINES_REPO="../project-guidelines"
mkdir -p .github/ISSUE_TEMPLATE
test -e README.md || cp "$GUIDELINES_REPO/templates/README.md" README.md
test -e .github/pull_request_template.md || cp "$GUIDELINES_REPO/.github/pull_request_template.md" .github/pull_request_template.md
test -e .github/ISSUE_TEMPLATE/bug_report.md || cp "$GUIDELINES_REPO/.github/ISSUE_TEMPLATE/bug_report.md" .github/ISSUE_TEMPLATE/bug_report.md
test -e .github/ISSUE_TEMPLATE/feature_request.md || cp "$GUIDELINES_REPO/.github/ISSUE_TEMPLATE/feature_request.md" .github/ISSUE_TEMPLATE/feature_request.md
# 변경 이력이 필요한 프로젝트에서만 실행합니다.
test -e CHANGELOG.md || cp "$GUIDELINES_REPO/templates/CHANGELOG.md" CHANGELOG.md
```

릴리스 노트는 [기본 양식](templates/RELEASE_NOTES.md)을 버전별 초안이나 GitHub Release 본문에 복사해 사용합니다. 실제 릴리스 게시·태그 생성·배포는 별도 작업이며 양식 복사로 실행되지 않습니다.

### 커밋 메시지 양식 연결하기

대상 프로젝트 루트에서 설정하면 그 저장소에만 적용됩니다. 에디터를 여는 `git commit`에서 표시하며, `git commit -m`에는 자동으로 붙지 않습니다.

```sh
git config --local commit.template "$(cd "$GUIDELINES_REPO" && pwd)/templates/commit-message.txt"
```

### GitHub Template 기능 사용하기

이 저장소의 **Use this template**로 문서와 양식 전체를 새 저장소에 가져올 수도 있습니다. 기존 앱 저장소에는 필요한 파일만 복사하는 방식을 권장합니다. 템플릿으로 만든 저장소에는 이 안내용 README가 들어가므로 앱을 만들 때는 `templates/README.md`로 시작해 실제 내용으로 교체하세요.

## 구성과 유지보수

`guidelines/`는 판단 기준의 원문, `templates/`는 복사하거나 참조하는 양식, `.github/`는 GitHub에서 바로 사용하는 PR·이슈 양식입니다. README 템플릿의 아키텍처 예시는 구성요소 선택에 도움이 되는 위치에 두며, 내부 구현 설명이 주목적이면 사용법 뒤로 옮깁니다.

공통 규칙의 원문은 이 저장소에서 관리합니다. 복사한 양식은 각 프로젝트가 관리하므로 원본 변경이 자동 반영되지 않습니다. 특정 버전의 기준을 고정하려면 문서 URL의 `main`을 검증한 커밋 SHA로 바꿀 수 있습니다.

이 저장소는 공개 프로젝트 문서와 Git 협업 기준·양식을 담당합니다. 별도의 엔지니어링·에이전트 지침 저장소가 있으면 해당 저장소는 코딩·설계·테스트·보안·도구별 실행 기준을 관리하고, README·커밋·PR·릴리스 작성 기준은 이 저장소의 원문을 링크합니다.

새 양식은 반복적으로 필요한 항목부터 추가합니다. API 문서와 보안 제보 안내 등은 프로젝트 성격과 실제 지원 정책이 정해졌을 때 확장합니다.
