# 큐밥(QBap) 출시용 법적·스토어 문서

## 개인정보처리방침 URL 올리기 (HTTPS)

Play Console에는 **공개 HTTPS URL**이 필요합니다. 아래 중 하나를 선택하세요.

### 방법 A: GitHub Pages (무료)

1. GitHub에 저장소를 만들고 `docs/legal/privacy-policy.html`을 푸시합니다.
2. 저장소 **Settings → Pages** → Source: **Deploy from branch** → Branch `main`, folder **`/docs`** 또는 **`/root`**.
   - `docs` 폴더만 배포하려면: Pages에서 **/docs** 루트를 쓰거나, `docs/legal`만 쓰려면 `docs`를 사이트 루트로 두고 URL은  
     `https://<사용자>.github.io/<저장소>/legal/privacy-policy.html`
3. Play Console **스토어 설정 → 개인정보처리방침**에 위 URL을 입력합니다.

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
