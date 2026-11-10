# 연세우리안과 안내 앱

환자 안내용 HTML 페이지를 앱으로 만든 프로젝트입니다. 화면 아래 탭으로 네 자료를 오갑니다.

- `www/index.html` — 백내장 수술 이야기 (첫 화면, `/`)
- `www/dreamlens.html` — 우리 아이 드림렌즈 (`/dreamlens`)
- `www/shingles.html` — 대상포진 예방접종 (`/shingles.html`)
- `www/dryeye.html` — 안구건조증 IPL 치료 (`/dryeye.html`)
- `www/tabs.css` — 하단 탭 모양

자료를 하나 더 추가하려면 HTML을 `www/`에 넣고, 각 페이지의 `<nav class='apptabs'>`에 링크를 추가한 뒤 `www/sw.js`의 `CORE` 목록과 `CACHE` 버전을 고칩니다.

| 형태 | 방법 |
|---|---|
| **웹앱 (Vercel)** | [vercel.com/new](https://vercel.com/new)에서 이 저장소를 Import → 설정은 그대로 두고 Deploy. 이후 push할 때마다 자동 배포됩니다. 휴대폰에서 주소를 열고 "홈 화면에 추가"하면 앱처럼 설치되고 오프라인에서도 볼 수 있습니다. (배포 설정: `vercel.json`, 배포 폴더 `www`) |
| **안드로이드 APK** | push할 때마다 Actions의 *Android APK* 작업이 APK를 빌드합니다. 실행 결과 페이지의 Artifacts에서 `cataract-story-debug-apk`를 받아 설치하세요. |
| **iOS** | Mac에서 `npm ci && npx cap sync ios && npx cap open ios` 후 Xcode에서 빌드합니다. |

## 내용 수정
1. `www/` 안의 HTML을 고칩니다.
2. `npx cap sync` (네이티브 앱에 반영)
3. 웹앱 캐시를 새로 받게 하려면 `www/sw.js`의 `CACHE` 버전을 올립니다.

## 로컬 미리보기
```bash
npm run serve   # http://localhost:8080
```

앱 ID: `kr.yonseiwoori.cataract` (`capacitor.config.json`). 스토어 출시용 서명 빌드는 키스토어를 만들어 `./gradlew bundleRelease`로 진행합니다.
