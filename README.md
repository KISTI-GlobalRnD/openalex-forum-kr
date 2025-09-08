# OpenAlex User Forum Korea (오픈알렉스 포럼 코리아)

한국 OpenAlex 사용자 커뮤니티의 행사/자료/네트워킹 허브를 목표로 하는 저장소입니다. 행사 소개와 일정, 발표자, 참가 신청 등은 `index.html`에서 관리하며, 튜토리얼·발표자료·커뮤니티 문서 등은 폴더별로 정리합니다.

- 라이브 페이지: GitHub Pages 활성화 후 공개 예정
- 참가 신청(구글 폼): https://docs.google.com/forms/d/e/1FAIpQLSdEQ4OgiJtCLmaz1hrWOoOqK_Y5RnVjWpVVSiKZ1tIri6apQA/viewform?usp=header

## 사이트 섹션 개요 (index.html)
- 오픈알렉스 소개: OpenAlex의 개요와 활용 포인트를 간단히 안내합니다.
- 행사 소개: 일시, 장소, 정원/시설, 대상 정보를 카드 형태로 제공합니다.
- 일정(Schedule): 시간표와 발표 주제/발표자를 표로 정리합니다.
- 발표자(Speakers): 사진(또는 이니셜)과 소속/주제를 카드로 표시합니다.
- 참가 신청(Registration): 구글 폼으로 이동하는 버튼을 제공합니다.
- 푸터(Footer): GitHub, 웹페이지, 이메일 링크를 제공합니다.

## 브랜드 로고/이미지 자산
- 위치: `img/`
  - `OpenAlex.webp`: 메인 브랜드 로고(표준 크기)
  - `OpenAlex-small.webp`: 헤더/푸터용 소형 로고
  - `OpenAlex-bg.webp`: 희미한 배경용(현재는 미사용)
- 사용처
  - 헤더: `OpenAlex-small.webp`를 텍스트 옆에 노출
  - 브랜드 섹션: 히어로 아래, OpenAlex 소개 위에 로고 단독 배치
  - 푸터: 소셜 링크 위에 소형 로고 표시
- 크기 조정
  - 헤더 로고: `.logo-img { height: 28px; }` 높이 수정
  - 브랜드 섹션 로고: `.brand-logo { max-width: 520px; }` 폭 수정
  - 푸터 로고: `style="max-height:40px"` 인라인 값 수정 가능

## 콘텐츠 업데이트 방법
- 일정 수정: `index.html`의 `#schedule` 섹션에서 각 `<tr>`의 시간/주제/발표자 텍스트를 직접 변경합니다.
- 발표자 관리: `#speakers` 섹션에서 `.speaker-card`를 복제/편집합니다.
  - 사진 추가: `.speaker-avatar` 내부에 `<img src="..." alt="이름 사진">`를 사용합니다. 정사각형 100×100 권장.
  - 사진이 없을 경우: `<span class="avatar-initial">T</span>` 형태로 영문 이니셜을 사용할 수 있습니다.
  - 순서 변경: 발표자 카드의 순서를 원하는 대로 재배치합니다.
- 참가 신청 링크: `id="google-form-btn"` 앵커의 `href`를 구글 폼 URL로 교체합니다(이미 설정됨).
- 소셜 링크: 푸터의 링크를 필요 시 교체합니다.

## 파일 편집 포인트
- 헤더 로고: `index.html`의 `.logo` 블록과 `.logo-img` 스타일
- 브랜드 섹션: `index.html`의 `section.brand-section` 및 `.brand-logo` 스타일
- 푸터 로고/링크: `index.html`의 `<footer>` 내부 링크 및 로고 이미지

## 저장소 구조
- `index.html`: 메인 정적 페이지(행사 소개/일정/발표자/신청 포함)
- `tutorials/`: OpenAlex/pyalex 관련 튜토리얼 자료
- `presentations/`: 포럼 발표 자료 및 리소스
- `community/`: 커뮤니티 가이드, 협업 프로젝트, Q&A 안내
- `resources/`: 유용한 링크/논문/도구 목록
- `events/`: 예정/지난 행사 정리 문서
- `.gitignore`, `.nojekyll`: 배포/버전관리 보조 파일

```
OpenAlex-Forum-KR/
├── index.html
├── tutorials/
│   ├── pyalex-basic.ipynb
│   ├── data-analysis-examples/
│   └── cheat-sheets/
├── presentations/
│   ├── 2025-09-forum-1/
│   └── resources/
├── community/
│   ├── discussions/
│   ├── collaboration-projects/
│   └── q-and-a/
├── resources/
│   ├── useful-links.md
│   ├── paper-recommendations.md
│   └── tools-and-libraries.md
└── events/
    ├── upcoming.md
    └── past-events/
```

## 로컬 미리보기
- 방법 1: `index.html` 파일을 브라우저로 직접 열기
- 방법 2: 간단 서버 사용 후 `http://localhost:8000` 접속
  - Python: `python3 -m http.server 8000`
  - Node(serve): `npx serve .`

## 배포(GitHub Pages)
1) GitHub 저장소 생성 후 로컬에서 초기 커밋/푸시
```
git init
git add -A
git commit -m "Initial site"
git remote add origin https://github.com/<org-or-user>/<repo>.git
git branch -M main
git push -u origin main
```
2) Settings → Pages → Source: `Deploy from a branch`, Branch: `main`, Folder: `/ (root)` 선택
3) 저장 후 몇 분 내 `index.html`이 공개됩니다. (루트에 `.nojekyll` 포함)

원하면 GitHub Actions로 자동 배포(또는 `gh-pages` 브랜치)도 설정할 수 있습니다.

## 링크
- GitHub(푸터): https://github.com/KISTI-GlobalRnD
- Webpage(푸터): https://dap.kisti.re.kr/globalrnd/
- Email(푸터): kimyoungjin06@kisti.re.kr

## 기여 원칙
- 한국어 우선, 필요한 경우 영어 용어 병기
- 문구/콘텐츠 변경은 PR로 제안(간단 수정은 직접 커밋도 가능)
- 이미지/자료는 관련 폴더 구조에 맞춰 추가

## 라이선스
필요 시 라이선스를 지정하세요(예: MIT, CC-BY). 현재 미정입니다.
