# 졸라맨 국가전략전 (Iron Front RTS)

한국·일본·미국 3개국이 등장하는 브라우저 기반 실시간 전략(RTS) 게임입니다.
서버·빌드 과정 없이 순수 HTML/JS로 동작해서, **깃허브에 올리기만 하면 링크 클릭으로 바로 플레이**할 수 있습니다.

## ⚡ 깃허브에 올리고 바로 플레이하기 (딱 한 번만 설정)

```bash
git init
git add .
git commit -m "졸라맨 국가전략전"
git branch -M main
git remote add origin https://github.com/<내계정>/<저장소이름>.git
git push -u origin main
```

**push 후 딱 한 번만** 아래 설정을 해주세요 (그 다음부턴 push할 때마다 자동으로 반영됩니다):

1. 저장소 페이지 → **Settings → Pages**
2. **Build and deployment → Source**를 `Deploy from a branch`로 두고,
   **Branch**를 `main` / `/ (root)`로 선택 → **Save**
3. 1~2분 기다리면 상단에 초록색 체크와 함께 주소가 뜹니다:
   ```
   https://<내계정>.github.io/<저장소이름>/
   ```
4. **그 주소를 클릭하면 바로 게임이 실행돼요.** 즐겨찾기/북마크 해두면 그 다음부턴 클릭 한 번으로 플레이!

> 이 저장소에는 `.github/workflows/deploy.yml`도 같이 들어있어서, Settings → Pages → Source를
> `GitHub Actions`로 바꾸면 push할 때마다 자동으로 재배포되는 방식도 선택할 수 있어요
> (둘 중 아무거나 하나만 쓰면 됩니다 — 정적 사이트라 `Deploy from a branch` 쪽이 더 간단해요).

모바일 브라우저로 그 주소에 들어간 뒤 **"홈 화면에 추가"**를 누르면 아이콘이 생겨서
앱처럼 바로 실행할 수도 있어요 (PWA).

## 📂 파일 구성

```
index.html                 게임 본체
manifest.json               PWA(설치형 웹앱) 설정
service-worker.js           오프라인 캐싱
icon-192.png / icon-512.png 앱 아이콘
.nojekyll                   깃허브 페이지가 파일을 그대로 서빙하도록 하는 설정 파일
.github/workflows/deploy.yml  (선택) 자동 배포 워크플로우
```

## 💻 로컬에서 바로 실행하기

`index.html`을 더블클릭해서 브라우저로 열면 그대로 플레이됩니다.

## 📱 진짜 APK 파일로 만들고 싶다면

깃허브 페이지로 호스팅한 주소가 생기면, 그 주소를 https://www.pwabuilder.com 에 입력 →
**Package for stores → Android**를 누르면 서명된 `.apk`/`.aab` 파일이 자동 생성돼서 다운로드됩니다.
(안드로이드 스튜디오 설치 없이 브라우저에서 끝나는 가장 쉬운 방법이에요.)

## 🎮 조작법 요약

- 좌클릭 드래그: 유닛 선택 / 더블클릭: 화면 내 동종 유닛 전체 선택
- 우클릭: 이동·채집·공격 / A: 공격 이동 / F(부대 선택 시): 대형 지정
- Q: 유휴 일꾼 순환 선택 / Ctrl+숫자: 부대 지정 / Shift+숫자: 화면 위치 저장
- Enter: 코드 입력창 (치트 코드)
