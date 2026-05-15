# 큐밥(QBap) 출시용 법적·스토어 문서

## 개인정보처리방침 URL 올리기 (HTTPS)

Play Console에는 **공개 HTTPS URL**이 필요합니다. 아래 중 하나를 선택하세요.

### 방법 A: GitHub Pages (무료)

1. GitHub에 저장소를 만들고 `docs/legal/privacy-policy.html`을 푸시합니다.
2. 저장소 **Settings → Pages** → **Build and deployment**
   - Source: **Deploy from a branch**
   - Branch: `main` (또는 사용 중인 기본 브랜치)
   - Folder: **`/docs`** ← 큐밥 저장소 구조에 맞음
3. 1~3분 후 Pages 상단에 나오는 주소를 확인합니다.

**올바른 URL (프로젝트 저장소, 예: 저장소 이름 `Qbap`)**

```
https://gjh999.github.io/Qbap/legal/privacy-policy.html
```

저장소 이름은 대소문자까지 GitHub와 동일해야 합니다.

**잘못된 URL (404 나는 경우)**

```
https://gjh999.github.io/docs/legal/privacy-policy.html   ← /docs/ 넣으면 안 됨
```

Pages에서 **Folder: /docs** 로 배포하면, GitHub는 `docs` **안의 파일**을 웹 루트에 올립니다.  
저장소 경로 `docs/legal/...` → 웹 주소는 `/legal/...` 이지 `/docs/legal/...` 가 아닙니다.

### `gjh999/docs` 저장소 (지금 스크린샷과 같은 구조)

저장소 **이름이 `docs`** 이고, 파일이 `docs/legal/privacy-policy.html` 이며, Pages가 **Branch `main` · Folder `/docs`** 일 때:

| 구분 | 주소 |
|------|------|
| 사이트 기본 주소 | `https://gjh999.github.io/docs/` |
| 개인정보처리방침 | **`https://gjh999.github.io/docs/legal/privacy-policy.html`** |

Pages 화면에 `https://gjh999.github.io/` 만 보여도, **프로젝트 저장소 `docs`** 는 위처럼 **`/docs/`가 URL에 한 번 더** 붙는 경우가 많습니다.  
반대로 사이트 루트가 정말 `gjh999.github.io` 라면 (드묾):

```
https://gjh999.github.io/legal/privacy-policy.html
```

**둘 중 브라우저에서 열리는 쪽**을 Play Console에 넣으면 됩니다.

#### 여전히 404일 때

1. GitHub **코드 탭**에서 `main` 브랜치에 `docs/legal/privacy-policy.html` 이 보이는지 확인 (로컬만 커밋하고 push 안 한 경우).
2. **Settings → Pages** → “Visit site” 또는 표시된 URL 클릭 → 주소창에 `/legal/privacy-policy.html` 붙여 보기.
3. **Actions** 탭에 Pages 빌드 실패가 없는지 확인.
4. `docs/.nojekyll` 파일이 있으면 Jekyll이 HTML을 건너뛰지 않습니다 (저장소에 push).
5. 저장 후 **1~5분** 기다렸다가 시크릿 창으로 다시 열기.

4. Play Console **스토어 설정 → 개인정보처리방침**에 **실제로 열리는** URL을 입력합니다.

#### 404일 때 체크

| 확인 | 조치 |
|------|------|
| Settings → Pages에 초록색 “사이트 게시됨” | 없으면 Branch·`/docs` 선택 후 Save |
| 저장소 Public | Private면 Pages 유료 플랜 필요 |
| 파일 경로 | `docs/legal/privacy-policy.html` 존재 |
| URL에 `/docs/` | **/docs 폴더 배포 시 제거** (`.../Qbap/legal/...`) |
| 배포 직후 | 1~5분 대기 후 새로고침 |

### 방법 B: Netlify / Cloudflare Pages

1. `docs/legal` 폴더를 드래그 앤 드롭 배포하거나 Git 연동.
2. `privacy-policy.html`이 루트에 오도록 publish directory를 `docs/legal`로 지정.
3. 예: `https://qbap-privacy.netlify.app/privacy-policy.html`

### 방법 C: 본인 도메인

회사·개인 도메인이 있으면 `https://www.example.com/privacy/qbap.html` 등으로 호스팅.

---

## Play Console에 넣을 URL (예시)

배포 후 실제 주소로 바꿔 넣으세요.

```
https://YOUR-HOST/legal/privacy-policy.html
```

---

## 데이터 안전(Data safety) 작성 시 참고

| Play 항목 | 큐밥 실제 동작 |
|-----------|----------------|
| 위치 | 대략적 위치, 앱 기능에 필수, 수집 O |
| 구매 기록 | 인앱 결제(커피 후원) |
| 광고 ID | AdMob 배너(후원 시 미표시) |
| 데이터 공유 | Google(Places, Play, AdMob), 운영 서버(결제 검증 시) |

개인정보처리방침 URL과 **동일한 내용**으로 설문에 답하는 것이 안전합니다.

---

## 출시 전 체크리스트

- [ ] 개인정보처리방침 HTTPS URL 확정·Play Console 입력
- [ ] 개발자 연락 이메일 `gjh999@hanmail.net` Play Console·스토어에 등록
- [ ] 릴리스 AAB + Play App Signing
- [ ] Places API (New) + 릴리스 SHA-1 키 제한
- [ ] AdMob 실제 단위 ID, 스토어 「광고 포함」
- [ ] 인앱 상품 `coffee_supporter` + 테스트 결제
- [ ] `BILLING_SERVER_BASE_URL` HTTPS 서버(권장) + `API_KEYS`
- [ ] 콘텐츠 등급·데이터 안전·스크린샷
- [ ] 내부 테스트 후 프로덕션 제출

자세한 순서는 루트 `AGENTS.md` 「스토어 출시」 절을 참고하세요.
