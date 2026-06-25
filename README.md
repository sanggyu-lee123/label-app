# 라벨 출력 PWA — GitHub Pages 배포 가이드

## 폴더 구성
```
label-pwa/
├── index.html      ← 앱 본체 (화면, 라벨 생성 로직)
├── manifest.json   ← PWA 설정 (앱 이름, 아이콘, 색상)
├── sw.js           ← 오프라인 캐싱용 서비스 워커
└── icons/
    ├── icon-192.png
    └── icon-512.png
```

## 1. GitHub 저장소 만들기
1. github.com 로그인 → 우측 상단 **+** → **New repository**
2. Repository name: `label-app` (원하는 이름으로 변경 가능)
3. **Public**으로 설정 (GitHub Pages 무료 사용을 위해 필요)
4. **Create repository** 클릭

## 2. 파일 업로드
1. 새로 만든 저장소 페이지에서 **uploading an existing file** 클릭
2. `label-pwa` 폴더 안의 파일/폴더를 전부 드래그해서 올리기
   (index.html, manifest.json, sw.js, icons 폴더 전체)
3. 하단 **Commit changes** 클릭

## 3. GitHub Pages 켜기
1. 저장소 상단 **Settings** 탭 클릭
2. 왼쪽 메뉴에서 **Pages** 클릭
3. **Branch** 를 `main` (또는 `master`), 폴더는 `/ (root)` 선택 → **Save**
4. 1~2분 기다리면 상단에 주소가 생김:
   `https://본인계정.github.io/label-app/`

## 4. 폰에서 설치하기
1. 폰 브라우저(Safari/Chrome)에서 위 주소 접속
2. **iOS (Safari)**: 하단 공유 버튼 → "홈 화면에 추가"
3. **Android (Chrome)**: 우측 상단 메뉴(⋮) → "홈 화면에 추가" 또는 "앱 설치"
4. 홈 화면에 생긴 아이콘을 누르면 앱처럼 바로 실행됨

## 나중에 수정하고 싶을 때
- `index.html`의 `teams` 배열에서 팀 이름/색상 추가·수정 가능
  ```js
  const teams = [
    { name: '최현재팀', color: [48, 48, 150] },
    // 여기에 추가...
  ];
  ```
- 수정 후 GitHub에 다시 업로드(Commit)하면 자동으로 배포 갱신됨 (1~2분 소요)
- 폰에 설치된 앱은 새로고침하면 최신 버전이 캐시에 반영됨

## 참고
- 완전히 정적인 앱이라 서버 비용 없음, GitHub Pages 평생 무료
- 입력한 데이터는 어디에도 저장되지 않고 그 화면에서만 사용됨
- 클립보드 복사 기능은 HTTPS 환경(GitHub Pages는 기본 HTTPS)에서만 동작함
