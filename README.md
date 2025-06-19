# 이화여자대학교 25-1 캡스톤 25조 팀 바위너구리


---

# AI 쓱싹비서 (AI-SS Assistant)

> “무엇을 언제 해야 할지 고민하지 않아도, 조금씩 매일 할 수 있도록 도와주는 AI 기반 생활 루틴 보조 서비스”

---

## 1. 프로젝트 소개

**AI 쓱싹비서**는 1인 가구 청년을 위한 **AI 기반 청소 루틴 추천 서비스**입니다.
사용자의 일정, 날씨, 생활 패턴 데이터를 바탕으로 매일 수행 가능한 **맞춤형 청소 루틴**을 추천하며,
게임화된 UI와 시각화된 피드백으로 **지속 가능한 생활 습관 형성**을 지원합니다.

---

## 2. 주요 기능

* **Google Calendar 연동**: 사용자의 일정을 자동으로 분석하여 루틴 스케줄에 반영
* **개인 설정 기반 루틴 추천**: 온보딩 설문과 사용자 설정을 통한 초기 루틴 생성
* **AI 기반 맞춤 루틴 생성**: 일정, 날씨, 청소 간격 등을 종합한 추천 루틴 도출
* **루틴 체크 및 피드백 수집**: 매일/매주 루틴 완료 여부 및 사용자의 정량적 피드백 수집
* **일주일 단위 루틴 시각화**: 일정에 녹아드는 루틴 UI 제공
* **강화학습 기반 루틴 최적화**: 사용자 피드백을 학습하여 루틴 정확도 향상

---

## 3. 시스템 구성도

```
[사용자]
   ⬇
[Frontend - React]
   ⬌ REST API ⬌
[Backend - Spring Boot] ⬌ [AI 서버 - FastAPI]
         ⬇
   [DB (RDS)] + [외부 API: Google, OpenWeather]
```

---

## 4. 프로젝트 구조 및 저장소

| 역할    | 저장소                                                                            | 설명                            |
| ----- | ------------------------------------------------------------------------------ | ----------------------------- |
| 프론트엔드 | [`AI-SS-ASSISTANT-FE`](https://github.com/TEAM-ROCKRACCOON/AI-SS-ASSISTANT-FE) | React 기반 사용자 UI               |
| 백엔드   | [`AI-SS-ASSISTANT-BE`](https://github.com/TEAM-ROCKRACCOON/AI-SS-ASSISTANT-BE) | Spring Boot 기반 API 서버         |
| AI 서버 | [`AI-SS-ASSISTANT-AI`](https://github.com/TEAM-ROCKRACCOON/AI-SS-ASSISTANT-AI) | FastAPI 기반 청소 루틴 생성 및 강화학습 서버 |

---

## 5. 기술 스택

| 영역           | 기술                                                                                       | 설명                   |
| ------------ | ---------------------------------------------------------------------------------------- | -------------------- |
| **Frontend** | React, TypeScript, Zustand, React Query, Tailwind CSS, Google OAuth, date-fns            | UI, 상태관리, 일정 연동      |
| **Backend**  | Java 17, Spring Boot 3.x, JPA, MySQL, Spring Security, OAuth2, OpenFeign, AWS EC2/RDS/S3 | API, 인증, DB 연동       |
| **AI 서버**    | Python, FastAPI, Pulp, Tianshou, NumPy, Pandas                                           | ILP 기반 스케줄링, 강화학습 모델 |
| **Infra**    | AWS EC2, RDS, S3                                                                         | 서버 및 데이터 저장소         |
| **외부 API**   | Google Calendar API, OpenWeatherMap API                                                  | 일정·날씨 정보 수집          |

---

## 6. 실행 방법

### \[프론트엔드]

```bash
git clone https://github.com/TEAM-ROCKRACCOON/AI-SS-ASSISTANT-FE.git
cd AI-SS-ASSISTANT-FE
npm install
npm run dev
```

### \[백엔드]

```bash
git clone https://github.com/TEAM-ROCKRACCOON/AI-SS-ASSISTANT-BE.git
cd AI-SS-ASSISTANT-BE
./gradlew build
java -jar build/libs/*.jar
```

### \[AI 서버]

```bash
git clone https://github.com/TEAM-ROCKRACCOON/AI-SS-ASSISTANT-AI.git
cd AI-SS-ASSISTANT-AI
pip install -r requirements.txt
uvicorn main:app --reload
```

---

## 7. 핵심 기술 요소

* **ILP 기반 스케줄링 (Pulp)**: 자투리 시간, 청소 필요도, 일정 피크를 고려한 최적 루틴 계산
* **사용자 행동 벡터**: 24x7 슬롯 기반 청소 수행 확률 모델링
* **정량적 피드백 수집**: 루틴 수행률 및 만족도(1\~5점)를 통한 RL 보상 설계
* **강화학습 기반 루틴 최적화 (Tianshou)**: 사용자 피드백 학습 → 루틴 재추천

---

## 8. 팀 구성

| 이름   | 역할      | 주요 담당                            |
| ---- | ------- | -------------------------------- |
| 이혜인 | 팀장, AI 개발자  | ILP 최적화, 사용자 벡터 설계, 강화학습 모델      |
| 고은서 | 프론트엔드, 디자이너   | 전체 UI 설계, 일정/루틴 시각화, 캘린더 연동, Figma 기반 UI/UX 설계, 캐릭터 디자인      |
| 황혜린 | 백엔드 | Spring Boot API 설계, 인증/일정/피드백 처리 |

---

## 9. 참고 자료

* [Google Calendar API Docs](https://developers.google.com/calendar)
* [OpenWeatherMap API](https://openweathermap.org/api)
* [Pulp Documentation](https://coin-or.github.io/pulp/)
* [Tianshou: RL Framework](https://tianshou.readthedocs.io/)

---
