# LG CNS team5 smart factory

## 개발 규칙

### 1. 브랜치 전략
**GitHub Flow 기반 + 릴리스 태깅**

- `main`: 항상 배포 가능한 안정 상태 유지
- 기능 개발: `feat/<scope>-<description>` 
  - 예: `feat/auth-login`, `feat/user-profile`
- 버그 수정: `fix/<scope>-<description>`
  - 예: `fix/api-timeout`, `fix/ui-button`
- 기타: `docs/`, `chore/`, `refactor/`, `test/` 등 목적별 프리픽스 사용
- **릴리스 태그**: `vX.Y.Z` (Semantic Versioning)
  - Patch (Z): 버그 수정
  - Minor (Y): 하위 호환 기능 추가
  - Major (X): 호환성 깨지는 변경

### 2. Pull Request 절차
1. **이슈 생성**: 작업 전 이슈를 먼저 등록하고 브랜치 생성
2. **PR 제목**: `type(scope): 간단한 설명` 형식 사용
3. **PR 체크리스트**:
   - [ ] 테스트/빌드 통과 확인
   - [ ] 자기 검토 완료 (로직, 에러 처리, 문서)
   - [ ] 변경 범위 최소화
   - [ ] 관련 문서 업데이트
   - [ ] 스크린샷/로그 첨부 (UI 또는 주요 변경사항)
4. **리뷰**: 최소 1명 이상 승인 필요
5. **머지 방식**: `Squash and merge` 권장 (커밋 히스토리 정리)
6. **머지 후**: 브랜치 삭제

### 3. 커밋 컨벤션
**Conventional Commits 사용**

형식: `type(scope): subject`

**주요 타입**:
- `feat`: 새로운 기능
- `fix`: 버그 수정
- `docs`: 문서 변경
- `style`: 코드 포맷팅 (로직 변경 없음)
- `refactor`: 리팩토링 (기능/버그 수정 아님)
- `perf`: 성능 개선
- `test`: 테스트 추가/수정
- `build`: 빌드 시스템 변경
- `ci`: CI 설정 변경
- `chore`: 기타 유지보수

**예시**:
```
feat(auth): 로그인 토큰 갱신 로직 추가
fix(api): 타임아웃 에러 핸들링 개선
docs(readme): 설치 가이드 업데이트
```

### 4. 코드 스타일 & 품질

#### 네이밍 컨벤션
- **변수**: camelCase (예: `userCount`, `isActive`)
- **함수/메서드**: camelCase (예: `fetchData`, `updateProfile`)
- **클래스/인터페이스/타입**: PascalCase (예: `UserService`, `AuthResponse`)
- **상수**: UPPER_SNAKE_CASE (예: `MAX_RETRY`, `DEFAULT_TIMEOUT`)
- **열거형(enum)**: PascalCase, 멤버는 PascalCase (예: `OrderStatus.Pending`)
- **파일명**: PascalCase (예: `UserService.ts`, `OrderController.py`)
- **폴더명**: PascalCase (예: `UserProfile`, `DataAccess`)
- **프라이빗 멤버**: 접두어 `_` 허용 (예: `_cache`)

### 5. 이슈 & 라벨 관리

**이슈 제목**: `[scope] 간단한 설명`
- 예: `[auth] 로그인 세션 만료 처리`


### 6. 보안 & 민감정보
- **금지**: 코드/이슈/PR에 API 키, 토큰, 비밀번호, 개인정보 포함 금지
- **환경변수**: `.env` 사용, 샘플은 `.env.example`로 공유

### 7. 규칙 변경 프로세스
- 규칙 수정 제안은 이슈로 등록 후 팀 논의
- 합의 후 PR로 문서 업데이트

---

규칙 관련 제안이나 질문은 이슈로 등록해 주세요.
