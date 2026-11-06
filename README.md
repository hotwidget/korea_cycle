# 두바퀴로 — 대한민국 자전거길 지도

별도의 빌드 도구 없이 `index.html`을 그대로 제공하는 정적 사이트입니다. GitHub Pages는 GitHub Actions로 배포합니다.

## GitHub Pages 배포

1. 이 폴더의 파일을 GitHub 저장소에 push합니다. 기본 브랜치는 `main`이어야 합니다.
2. 저장소의 **Settings → Pages → Build and deployment → Source**에서 **GitHub Actions**를 선택합니다.
3. `main` 브랜치에 push하면 `.github/workflows/pages.yml`이 `index.html`을 배포합니다. **Actions** 탭에서 배포 완료와 공개 주소를 확인할 수 있습니다.

워크플로는 홈페이지 파일만 배포하므로 `.venv`와 개발용 파일은 사이트에 포함되지 않습니다. 코드를 바꾼 뒤 `main`에 push하면 자동으로 다시 배포됩니다.

## 로컬에서 보기

프로젝트 폴더에서 다음 명령을 실행하고 `http://127.0.0.1:8080/`을 엽니다.

```powershell
python -m http.server 8080 --bind 127.0.0.1
```

지도 타일과 Leaflet, 글꼴은 외부 서비스에서 가져오므로 인터넷 연결이 필요합니다. 위치 찾기 기능은 브라우저의 위치 권한을 사용합니다.
