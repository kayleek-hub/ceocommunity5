# 사장님커뮤니티 5기 FAQ — 외부 공개 배포 안내 (GitHub Pages)

이 폴더가 **그대로 하나의 웹사이트**입니다. 이 안의 파일을 GitHub 저장소에 올리고 Pages를 켜면, 카카오 임직원이 아닌 **사장님들도 로그인 없이** 볼 수 있는 공개 주소가 생깁니다.

## 폴더 구성

| 파일 | 역할 |
| --- | --- |
| `index.html` | 5기 FAQ 메인 (검색 + AI 추천 답변). 접속 시 처음 열리는 페이지 |
| `curriculum.html` | 5기 커리큘럼 |
| `results4.html` | 4기 성과 페이지 |
| `assets/` | 위 3개 페이지에서 쓰는 이미지 5개 |
| `robots.txt` | 검색엔진 수집 허용 |
| `.nojekyll` | GitHub의 불필요한 후처리를 끄는 빈 파일 (없어도 동작합니다) |
| `DEPLOY.md` | 이 안내문. 사이트 화면에는 나타나지 않습니다 |

모든 링크와 이미지 경로가 **상대경로**라 저장소 이름이 무엇이든 그대로 동작합니다.

## 방법 A — 브라우저만으로 (가장 쉬움, 5분)

1. github.com 로그인 → 우측 상단 `+` → **New repository**
2. 저장소 이름은 예를 들어 `ceocommunity5`, 공개 범위는 반드시 **Public** (Pages 무료 배포는 Public 기준)
3. 만들어진 저장소 화면에서 **Add file → Upload files**
4. 이 폴더 안의 `index.html`, `curriculum.html`, `results4.html`, `robots.txt`와 **`assets` 폴더째로** 끌어다 놓기 → `Commit changes`
   - `DEPLOY.md`는 올리지 않아도 되고, 올려도 사이트 화면에는 영향이 없습니다.
   - `.nojekyll`은 맥 파인더에서 숨어 있어 안 올라갈 수 있는데, 없어도 정상 동작합니다.
5. 저장소 상단 **Settings → 좌측 Pages** → Source는 `Deploy from a branch`, Branch는 `main` / `/ (root)` → **Save**
6. 1~2분 뒤 같은 화면 위쪽에 주소가 뜹니다 : `https://<깃허브아이디>.github.io/ceocommunity5/`

## 방법 B — 터미널에서 (git 명령)

```bash
cd ~/Downloads/deploy-ceocommunity5   # 이 폴더를 저장한 위치로 이동
git init -b main
git add -A
git commit -m "사장님커뮤니티 5기 FAQ 공개 페이지"
git remote add origin https://github.com/<깃허브아이디>/ceocommunity5.git
git push -u origin main
```

push 후 **Settings → Pages**에서 5번과 같이 `main` / `/ (root)`로 설정하면 됩니다.

## 공개 후 확인할 것

1. 발급된 주소를 **시크릿 창**(로그인 안 된 상태)에서 열어 확인 → 이게 사장님들이 보는 화면입니다.
2. 휴대폰에서도 한 번 열어보기 (모바일 기준으로 맞춰둔 페이지입니다)
3. `index.html` 하단 카테고리 버튼, 검색, AI 추천 답변, 다음카페·오픈채팅 버튼이 모두 열리는지
4. `curriculum.html`·`results4.html`로 넘어가는 링크가 동작하는지

## 나중에 내용을 고칠 때

- 간단한 수정 : 저장소에서 해당 `.html` 파일을 열고 GitHub의 연필(✏️) 아이콘으로 고친 뒤 `Commit changes` → 1분 내 반영
- 제가 파일을 갱신해 드린 경우 : 같은 파일명으로 **Add file → Upload files**로 덮어쓰면 됩니다
- 반영이 안 보이면 브라우저 캐시 때문이니 강제 새로고침(⌘⇧R)

## 배포 전 한 번 더 봐주실 부분

- 공개 주소가 생기면 누구나 볼 수 있으니, **아직 확정되지 않은 일정·금액이 남아 있지 않은지** 페이지를 한 번 훑어봐 주세요. (사전 설정 VOD는 실제 주소로 연결해두었고, 2주차 이후 실습 튜토리얼 VOD 자리는 주소가 나올 때까지 비워둔 상태입니다)
- 내부 자료(4기 내부 보고자료 슬라이드, 내부 가이드 덱, 예약하기 수수료율 등)는 의도적으로 **제외**했습니다. 공개 페이지에 다시 넣지 않도록 주의해주세요.
