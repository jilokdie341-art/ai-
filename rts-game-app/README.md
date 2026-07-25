# 졸라맨 국가전략전 (Iron Front RTS)

한국·일본·미국 3개국이 등장하는 브라우저 기반 실시간 전략(RTS) 게임입니다.
순수 HTML/CSS/JavaScript(Canvas)로 만들어져 있어 서버나 빌드 과정 없이 그대로 실행됩니다.

## 📂 파일 구성

```
index.html          게임 본체 (여기에 모든 로직이 들어있음)
manifest.json        PWA(설치형 웹앱) 설정
service-worker.js    오프라인 캐싱
icon-192.png / icon-512.png   앱 아이콘
```

## ▶ 로컬에서 실행하기

`index.html`을 더블클릭해서 브라우저로 열면 바로 플레이할 수 있습니다.
(단, 서비스워커/설치 기능은 `file://`로 열면 브라우저 정책상 제한될 수 있어서,
아래처럼 로컬 서버로 띄우는 걸 권장합니다.)

```bash
# 이 폴더 안에서
python3 -m http.server 8080
# 브라우저에서 http://localhost:8080 접속
```

## 🐙 깃허브에 올리기

```bash
git init
git add .
git commit -m "졸라맨 국가전략전 초기 업로드"
git branch -M main
git remote add origin https://github.com/<내계정>/<저장소이름>.git
git push -u origin main
```

## 🌐 깃허브 페이지로 무료 호스팅 (선택)

1. 저장소 **Settings → Pages**
2. Source를 `main` 브랜치 `/ (root)`로 설정
3. 몇 분 뒤 `https://<계정>.github.io/<저장소이름>/` 주소로 바로 플레이 가능
4. 모바일 브라우저에서 이 주소로 접속하면 "홈 화면에 추가"로 앱처럼 설치 가능 (PWA)

## 📱 진짜 APK 파일로 만들기

이 대화 환경에는 안드로이드 빌드 도구(Android SDK/Gradle)와 인터넷 접근이 없어서
`.apk`를 여기서 직접 컴파일할 수는 없었어요. 대신 위에서 만든 웹앱을 실제 APK로
바꾸는 가장 쉬운 방법은 아래 두 가지입니다 (둘 다 무료):

### 방법 1: PWABuilder (제일 쉬움, 설치 없이 웹에서 끝)
1. 위 "깃허브 페이지"로 먼저 호스팅해서 실제 URL을 하나 만든다
2. https://www.pwabuilder.com 접속 → 그 URL 입력
3. "Package for stores" → **Android** 선택
4. 몇 초 뒤 서명된 `.apk` / `.aab` 파일이 자동으로 생성되어 다운로드됨

### 방법 2: Bubblewrap CLI (터미널 선호 시)
```bash
npm install -g @bubblewrap/cli
bubblewrap init --manifest=https://<내주소>/manifest.json
bubblewrap build
```
빌드가 끝나면 `app-release-signed.apk`가 생성됩니다.

두 방법 다 Node.js/자바 등 안드로이드 툴체인이 필요한데, 이건 여러분 컴퓨터(또는
PWABuilder처럼 브라우저에서 대신 처리해주는 서비스)에서 진행하시면 됩니다.

## 🎮 조작법 요약

- 좌클릭 드래그: 유닛 선택 / 더블클릭: 화면 내 동종 유닛 전체 선택
- 우클릭: 이동·채집·공격 / A: 공격 이동 / F(부대 선택 시): 대형 지정
- Q: 유휴 일꾼 순환 선택 / Ctrl+숫자: 부대 지정 / Shift+숫자: 화면 위치 저장
- Enter: 코드 입력창 (치트 코드)
