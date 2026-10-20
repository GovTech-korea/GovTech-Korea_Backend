# GovTech-Korea Backend

GovTech Korea 공모전 출품작의 백엔드 서버입니다.

## 기술 스택

| 항목 | 버전 |
|---|---|
| Java | 25 |
| Spring Boot | 4.1.1 |
| 빌드 도구 | Gradle 9 (Groovy DSL) |
| 주요 의존성 | Spring Web MVC, Validation, Lombok, DevTools |

## 실행 방법

JDK 25가 설치되어 있어야 합니다. 기본 JDK가 다른 버전이어도 Gradle toolchain이 설치된 JDK 25를 찾아 빌드합니다.
찾지 못하면 `~/.gradle/gradle.properties`에 `org.gradle.java.installations.paths=<JDK 25 경로>`를 지정합니다.

```bash
./gradlew bootRun        # 실행 (http://localhost:8080)
./gradlew build          # 컴파일 + 전체 테스트
./gradlew test           # 테스트만
```

## 브랜치와 PR 규칙

```
작업 브랜치 ──PR──▶ develop ──PR (통합 테스트 후)──▶ main
```

- `main`, `develop`에는 직접 push할 수 없고, PR로만 반영합니다.
- 작업 브랜치 이름: `<타입>/<이슈번호>-<설명>` (예: `feat/12-sign-up-api`)
- 커밋 메시지: `<타입>: <한글 설명>` (예: `feat: 회원가입 API 추가`)
- PR은 CI(`branch-flow`, `build`)를 통과해야 머지할 수 있고, 머지는 merge commit 방식만 사용합니다.
