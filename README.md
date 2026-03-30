# 🎵 응원곡 레슨 캘린더

멤버별 응원곡 레슨 일정을 관리하고 공유할 수 있는 웹 캘린더입니다.  
서버 없이 GitHub Gist를 통해 데이터를 저장하며, 모든 멤버가 하나의 캘린더를 함께 사용합니다.

## 주요 기능

- **멤버별 일정 관리** — 멤버마다 고유 색상으로 구분되는 레슨 일정
- **매주 반복 일정** — 요일/시간을 지정하면 기간 내 자동 생성 (예: 매주 화·목 14시)
- **자동 동기화** — 일정 변경 시 즉시 Push, 30초마다 자동 Pull, 탭 전환 시 즉시 갱신
- **단일 캘린더** — 같은 토큰 + Gist ID를 입력하면 모든 기기에서 동일한 캘린더 사용
- **단일 파일** — `index.html` 하나로 동작, 별도 서버 불필요

## 시작하기

### 1. GitHub Personal Access Token 발급

1. GitHub → **Settings** → **Developer settings** → **Personal access tokens** → **Tokens (classic)**
2. **Generate new token** 클릭
3. 권한에서 **`gist`** 체크 → 토큰 생성
4. 생성된 `ghp_...` 토큰을 복사해 둡니다

### 2. 최초 연결 (캘린더 생성)

1. 캘린더 우측 상단 **⚙️ 설정** 클릭
2. 토큰 입력 → Gist ID는 비워두기 → **연결** 클릭
3. 자동으로 Gist가 생성되고 Gist ID가 표시됩니다

### 3. 다른 기기 / 멤버 연결

1. 설정 화면에 표시된 **Gist ID**를 복사
2. 다른 기기나 멤버에게 **토큰**과 **Gist ID**를 공유
3. 같은 토큰 + Gist ID를 입력하면 동일한 캘린더에 접속됩니다

## 배포 방법

단일 HTML 파일이므로 정적 호스팅이면 충분합니다.

### GitHub Pages (추천)

```bash
git init
git add index.html
git commit -m "init"
git branch -M main
git remote add origin https://github.com/[사용자명]/[레포명].git
git push -u origin main
```

레포 **Settings → Pages → Source**를 `main`으로 설정하면  
`https://[사용자명].github.io/[레포명]/` 에서 접속할 수 있습니다.

### Netlify

`index.html`이 있는 폴더를 [Netlify Drop](https://app.netlify.com/drop)에 드래그 앤 드롭하면 즉시 배포됩니다.

### Vercel

GitHub 레포 생성 후 [Vercel](https://vercel.com)에서 Import하면 자동 배포됩니다.

## 파일 구조

```
/
├── index.html    ← 캘린더 앱 (이 파일 하나가 전부입니다)
└── README.md
```

## 기술 스택

- HTML / CSS / Vanilla JavaScript
- GitHub Gist API (데이터 저장)
- LocalStorage (오프라인 캐시)

## 라이선스

MIT
