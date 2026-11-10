# 백내장 수술 이야기 앱 (연세우리안과)

환자 안내용 HTML 페이지(`www/index.html`)를 앱으로 만든 프로젝트입니다.

| 형태 | 방법 |
|---|---|
| **웹앱 (PWA)** | `main` 브랜치에 올리면 GitHub Pages로 배포됩니다. 휴대폰 브라우저에서 열고 "홈 화면에 추가"하면 앱처럼 설치되고, 한 번 열면 오프라인에서도 볼 수 있습니다. (저장소 Settings → Pages → Source를 **GitHub Actions**로 설정) |
| **안드로이드 APK** | push할 때마다 Actions의 *Android APK* 작업이 APK를 빌드합니다. 실행 결과 페이지의 Artifacts에서 `cataract-story-debug-apk`를 받아 설치하세요. |
| **iOS** | Mac에서 `npm ci && npx cap sync ios && npx cap open ios` 후 Xcode에서 빌드합니다. |

## 내용 수정
1. `www/index.html`을 고칩니다.
2. `npx cap sync` (네이티브 앱에 반영)
3. 웹앱 캐시를 새로 받게 하려면 `www/sw.js`의 `CACHE` 버전을 올립니다.

## 로컬 미리보기
```bash
npm run serve   # http://localhost:8080
```

앱 ID: `kr.yonseiwoori.cataract` (`capacitor.config.json`). 스토어 출시용 서명 빌드는 키스토어를 만들어 `./gradlew bundleRelease`로 진행합니다.
