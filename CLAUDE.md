# 행복한 하루 — CLAUDE.md

## 프로젝트 개요
날씨 기반 문화·일상 추천 웹앱. 현재 날씨에 맞는 음악·시·명화·장소·책·활동을 추천한다.
순수 HTML/CSS/JS (프레임워크 없음). 외부 서버 없이 GitHub Pages에 정적 배포.

## 파일 구조
```
C:\Users\USER\happy_day\
├── index.html      # 오늘 날씨 기반 추천
├── monthly.html    # 16일 예보 달력 + 날짜별 추천
├── CLAUDE.md       # 이 파일
├── weather.md      # 날씨 조건·테마 정리
├── content-db.md   # 콘텐츠 DB 구조 (음악/시/그림/명언)
├── api.md          # Open-Meteo API 사용법
├── deployment.md   # GitHub Pages 배포 정보
└── bugs.md         # 알려진 버그 및 해결 기록
```

## 배포 URL
- 오늘 날씨: https://choisuka.github.io/Happy-day/
- 16일 예보: https://choisuka.github.io/Happy-day/monthly.html

## 핵심 구조 (두 파일 공통)
- **날씨 감지**: Open-Meteo API → `weather_code` → `getCondition()` 함수로 8가지 조건 중 하나 반환
- **콘텐츠 선택**: `pick(arr)` — 연중 몇 번째 날(day-of-year) % 배열 길이로 매일 다른 항목 선택
- **테마**: `document.body.className = condition` → CSS 변수로 색상 자동 변경
- **탭 전환**: `showTab(name)` — `.panel.active` 클래스 토글

## 개발 환경
- 별도 빌드 없음. HTML 파일을 브라우저로 열면 바로 동작
- 위치 정보: `navigator.geolocation` → Open-Meteo API 호출
- Git 저장소: `C:\Users\USER\happy_day\` (GitHub: choisuka/Happy-day)