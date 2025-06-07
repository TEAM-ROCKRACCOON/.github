# 이화여자대학교 25-1 캡스톤 25조 팀 바위너구리

---

````markdown
# AI-SS-ASSISTANT

**AI 쓱싹비서**는 사용자의 생활 패턴, 고정 일정, 날씨 데이터를 기반으로  
**개인화된 청소 및 위생 루틴을 추천**하고 지속적으로 최적화하는 AI 기반 라이프스타일 테크 서비스입니다.

> 스케줄 + 날씨 + AI 추천 = 생활 최적화

---

## 프로젝트 개요

| 항목 | 내용 |
|------|------|
| 팀명 | Team 25 바위너구리 |
| 주제 | 개인 생활패턴을 고려한 맞춤형 청소 & 위생 루틴 추천 AI 서비스 |
| 목적 | 바쁜 현대인이 청소 부담 없이 위생적 환경을 유지하도록 돕는 AI 비서 |
| 핵심 기능 | 온보딩 → 일정 수집 → 청소 추천 → 루틴 수행 → 피드백 학습 |

---

## 프로젝트 구성

```bash
AI-SS-ASSISTANT/
├── frontend/         # 사용자 웹 앱 (React)
├── backend/          # API 서버 및 DB 처리 (Spring Boot)
├── ai/               # 루틴 최적화 및 강화학습 엔진 (Python)
└── README.md         # 프로젝트 메인 설명 파일
````

---

## 프론트엔드 (frontend)

* **주요 기술**: React, TypeScript, Zustand, React Query, Tailwind CSS
* **핵심 기능**:

  * Google 로그인 및 캘린더 연동
  * 온보딩: 주거정보, 청소 선호도, 생활 습관 입력
  * 루틴 뷰어: 오늘 할 일 / 일주일 루틴 확인 및 체크
  * 피드백 입력 → 달성률 시각화
* **저장소**: [`AI-SS-ASSISTANT-FE`](https://github.com/TEAM-ROCKRACCOON/AI-SS-ASSISTANT-FE)

---

## 백엔드 (backend)

* **주요 기술**: Spring Boot, MySQL, AWS S3, REST API
* **기능 요약**:

  * 사용자/루틴/일정 정보 저장 및 조회
  * 초기 루틴 생성 요청 처리
  * 강화학습 결과 반영된 루틴 업데이트
  * S3를 통한 이미지 저장(추후 확장 가능)
* **저장소**: [`AI-SS-ASSISTANT-BE`](https://github.com/TEAM-ROCKRACCOON/AI-SS-ASSISTANT-BE)

---

## AI 루틴 추천 엔진 (ai)

* **주요 기술**: Python, PuLP (ILP), Tianshou (RL), Stable-Baselines3
* **구현 방식**:

  1. ILP 기반 초기 루틴 생성 (사용자 일정 + 주기 조건 기반 최적화)
  2. 사용자 수행 기록과 피드백 → RL 학습 데이터 생성
  3. DQN 기반 강화학습 모델로 루틴 조정
  4. 미세먼지·습도 등 날씨 데이터 반영하여 동적 루틴 조정
* **저장소**: [`AI-SS-ASSISTANT-AI`](https://github.com/TEAM-ROCKRACCOON/AI-SS-ASSISTANT-AI)

---

## 외부 API 연동

| API                 | 목적                           |
| ------------------- | ---------------------------- |
| Google Calendar API | 사용자의 고정 일정 수집                |
| OpenWeatherMap API  | 미세먼지, 강수량 등 기상 정보 수집 및 루틴 조정 |
| AWS S3              | 이미지, 자료 저장               |

---

## 시연 영상

* **유튜브 링크**: [시연 영상 보기](https://youtu.be/aJ9WD01Mdj4)
* **구성 방식**:

  * 좌측: 피그마 UI, 우측: 코드 흐름 및 설명
  * 강화학습 전후 루틴 차이 예시
  * 사용자 피드백 → 학습 → 루틴 반영 흐름 포함
* **PPT 기반 캡쳐 + 자막 + 음성 포함**
* **요약 PDF**: `링크추가예정`

---

## 실행 순서

1. `frontend/`에서 클라이언트 실행: `npm install && npm run dev`
2. `backend/`에서 Spring Boot 서버 실행
3. `ai/`에서 루틴 생성 및 강화학습 파이프라인 실행
4. 프론트에서 루틴 요청 → 백엔드 → AI → 루틴 반환 → 화면 표시

---

## 팀 정리 및 역할

| 이름  | 역할                       |
| --- | ------------------------ |
| 고은서 | 프론트엔드, 피그마 설계, 시각화 UI 구성 |
| 황혜린 | 벡엔드,    |
| 이혜인 | AI 루틴 추천 로직 및 강화학습 설계    |

---

## 제출 정보

* 프로젝트 Repo URL: [https://github.com/TEAM-ROCKRACCOON/AI-SS-ASSISTANT](https://github.com/TEAM-ROCKRACCOON/AI-SS-ASSISTANT)
* 시연 영상 URL: (https://youtu.be/aJ9WD01Mdj4)
* 제출 파일: `링크추가예정`

```

---

```

