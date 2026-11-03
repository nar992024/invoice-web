---
description: '이모지와 컨벤셔널 커밋 메시지로 잘 포맷된 커밋을 생성합니다'
allowed-tools:
  [
    'Bash(git add:*)',
    'Bash(git status:*)',
    'Bash(git commit:*)',
    'Bash(git diff:*)',
    'Bash(git log:*)',
  ]
---

# Claude 명령어: Commit

이모지와 컨벤셔널 커밋 메시지로 잘 포맷된 커밋을 생성합니다.

## 사용법

```
/commit
```

## 프로세스

1. 스테이지된 파일 확인, 스테이지된 파일이 있으면 해당 파일만 커밋
2. 여러 논리적 변경사항에 대한 diff 분석
3. 필요시 분할 제안
4. 이모지 컨벤셔널 포맷으로 커밋 생성

## 커밋 포맷

`<이모지> <타입>: <설명>`

**타입:**

변경 내용을 가장 구체적으로 나타내는 타입을 하나 고릅니다. 타입별 이모지는 이모지 맵을 따릅니다.

기능과 사용자 경험:

- `feat`: 새로운 기능
- `business`: 비즈니스 로직 추가 또는 변경
- `ux`: 사용성과 사용자 경험 개선
- `accessibility`: 접근성 개선
- `animations`: 애니메이션과 전환 효과
- `analytics`: 분석과 추적 코드
- `flags`: 기능 플래그 추가 또는 변경
- `offline`: 오프라인 지원
- `experiment`: 실험적인 변경

수정:

- `fix`: 버그 수정
- `minor-fix`: 간단한 수정
- `hotfix`: 긴급한 운영 문제 수정
- `typos`: 오타 수정
- `errors`: 에러 처리 추가 또는 개선
- `validation`: 입력값과 데이터 검증
- `warnings`: 컴파일러와 린터 경고 해결
- `security`: 보안 문제 수정

구조 변경:

- `refactor`: 동작을 유지한 코드 리팩토링
- `structure`: 코드 구조와 형식 개선
- `architecture`: 아키텍처 변경
- `move`: 파일, 경로, 이름 변경
- `remove`: 코드나 파일 삭제
- `dead-code`: 사용하지 않는 코드 삭제
- `types`: 타입 추가 또는 수정

성능, 문서, 스타일:

- `perf`: 성능 개선
- `docs`: 문서화
- `comments`: 코드 주석 추가 또는 수정
- `license`: 라이선스 추가 또는 변경
- `style`: 동작에 영향이 없는 포맷팅

테스트:

- `test`: 테스트 추가 또는 수정
- `snapshots`: 스냅샷 추가 또는 갱신

데이터와 로그:

- `db`: 데이터베이스 스키마와 쿼리 변경
- `seed`: 시드 데이터 추가 또는 변경
- `logs`: 로그 추가 또는 수정
- `remove-logs`: 로그 삭제

의존성:

- `add-dep`: 의존성 추가
- `remove-dep`: 의존성 삭제
- `pin-deps`: 의존성 버전 고정

빌드, CI, 도구:

- `chore`: 다른 타입에 해당하지 않는 빌드와 도구 작업
- `ci`: CI 설정 변경
- `ci-build`: CI 빌드 시스템 변경
- `ci-fix`: CI 실패 수정
- `dx`: 개발자 경험 개선
- `gitignore`: `.gitignore` 변경
- `assets`: 이미지 등 정적 파일 추가 또는 변경

릴리스와 이력:

- `init`: 프로젝트 초기 구성
- `release`: 릴리스와 버전 태그
- `wip`: 진행 중인 작업
- `revert`: 이전 변경 되돌리기
- `breaking`: 호환성을 깨는 변경

**규칙:**

- 명령형 어조 ("추가" not "추가됨")
- 첫 줄 72자 미만
- 원자적 커밋 (단일 목적)
- 관련 없는 변경사항 분할

## 이모지 맵

✨ feat | 🐛 fix | 📝 docs | 💄 style | ♻️ refactor | ⚡ perf | ✅ test | 🔧 chore | 🚀 ci | 🚨 warnings | 🔒️ security | 🚚 move | 🏗️ architecture | ➕ add-dep | ➖ remove-dep | 🌱 seed | 🧑‍💻 dx | 🏷️ types | 👔 business | 🚸 ux | 🩹 minor-fix | 🥅 errors | 🔥 remove | 🎨 structure | 🚑️ hotfix | 🎉 init | 🔖 release | 🚧 wip | 💚 ci-fix | 📌 pin-deps | 👷 ci-build | 📈 analytics | ✏️ typos | ⏪️ revert | 📄 license | 💥 breaking | 🍱 assets | ♿️ accessibility | 💡 comments | 🗃️ db | 🔊 logs | 🔇 remove-logs | 🙈 gitignore | 📸 snapshots | ⚗️ experiment | 🚩 flags | 💫 animations | ⚰️ dead-code | 🦺 validation | ✈️ offline

## 분할 기준

다른 관심사 | 혼합된 타입 | 파일 패턴 | 큰 변경사항

## 참고사항

- 스테이지된 파일이 있으면 해당 파일만 커밋
- 분할 제안을 위한 diff 분석
- **커밋에 Claude 서명 절대 추가하지 않음**
