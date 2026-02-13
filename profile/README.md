# 🎙️ VoiceTwin – AI 음성 복제 및 실시간 번역 플랫폼

> 사용자의 목소리 톤을 유지한 채 전 세계 언어로 실시간 통번역을 지원하는 AI 서비스입니다.

## 📌 프로젝트 개요
VoiceTwin은 단순한 텍스트 번역을 넘어, **AI Voice Cloning** 기술을 통해 화자의 고유한 목소리 특성을 유지하면서 다국어 음성을 생성합니다. 글로벌 소통에서 언어의 장벽을 허물고 화자의 감정과 정체성을 보존하는 혁신적인 커뮤니케이션 경험을 제공합니다.

<!--
## 📺 시연 영상
[▶️ VoiceTwin 시연 영상 보러가기](영상_링크_주소)
-->
## 🚀 Live Demo
- **Frontend**: [VoiceTwin Online](https://voicetwin-front.vercel.app/login)
- **Status**: Deployment via Vercel
---

## 🛠 기술 스택
## 🏛️ System Architecture & Flow
VoiceTwin은 React, Spring Boot, FastAPI 그리고 외부 AI 모델 간의 유기적인 시퀀스를 통해 실시간 통번역을 수행합니다.

<div align="center">
  <img src="https://github.com/user-attachments/assets/9f5fa0a1-b21e-4fed-9b8b-d5e2b8e632b1" width="90%" alt="VoiceTwin Architecture Sequence Diagram" />
  <p><i>[VoiceTwin 서비스 아키텍처 및 데이터 흐름도]</i></p>
</div>

1.  **React (5173)**: 사용자의 음성 데이터와 목표 언어를 수집하여 메인 백엔드로 전송합니다.
2.  **Spring Boot (8080)**: 사용자의 인증(JWT)을 검증하고 AI 엔진으로 요청을 라우팅합니다.
3.  **FastAPI AI (8000)**: OpenAI(STT, GPT) 및 ElevenLabs(Voice Clone)와 통신하여 AI 파이프라인을 처리합니다.
4.  **Result**: 최종 번역된 텍스트 메타데이터와 복제된 목소리 오디오(MPEG)를 사용자에게 반환합니다.
### AI & Speech Processing
- **Python (FastAPI)**: 고성능 비동기 AI API 서버 구축
- **OpenAI Whisper**: 고정밀 음성 인식(STT) 및 텍스트 추출
- **ElevenLabs API**: Zero-shot 기반 고성능 음성 복제(Voice Cloning) 및 합성(TTS)
- **GPT-4o**: 맥락을 고려한 자연스러운 다국어 번역 엔진
- **FFmpeg**: 실시간 오디오 포맷 변환 및 샘플링 처리

### Backend
- **Spring Boot (Java)**: 메인 비즈니스 로직 및 API 게이트웨이
- **Spring Security + JWT**: 사용자 인증 및 보안 체계 구축
- **JPA (Hibernate)**: 데이터베이스 계층 관리 및 ORM 적용
- **PostgreSQL**: 유저 정보 및 음성 데이터 메타데이터 저장
- **Redis**: 실시간 데이터 처리 및 캐싱

### Frontend
- **React (Vite)**: 빠르고 현대적인 사용자 경험 제공
- **Tailwind CSS**: 유틸리티 중심의 반응형 UI 디자인
- **Axios**: 백엔드 및 AI 서버와의 비동기 통신

### Infra & DevOps
- **Docker**: 컨테이너화를 통한 AI 모델 및 서버 환경 일관성 유지
- **AWS EC2**: 탄력적인 클라우드 컴퓨팅 인프라 활용
- **GitHub Actions**: 코드 자동 빌드 및 배포 파이프라인(CI/CD) 구축

---

## ✨ 주요 기능
- **실시간 음성 복제**: 10초 내외의 샘플로 사용자의 목소리 특징 추출
- **다국어 실시간 번역**: 한국어 음성을 영어, 일본어 등 다양한 언어로 즉시 변환
- **감정 유지 합성**: 원본 음성의 톤과 억양을 반영한 자연스러운 음성 생성
- **히스토리 관리**: 과거 번역된 텍스트 및 음성 파일 보관 기능

---

## 📂 시스템 아키텍처


- **Client**: 녹음된 오디오 전송 및 결과 오디오 재생
- **Spring Backend**: 사용자 인증(JWT), 데이터 저장 및 요청 라우팅
- **AI Server (FastAPI)**: STT -> Translation -> Voice Cloning -> TTS 파이프라인 처리

---

## 💡 배운 점 & 트러블슈팅
- **AI 서버 응답 지연 최적화**: FastAPI의 비동기 처리를 통한 오디오 처리 병목 현상 해결
- **CORS & 보안 설정**: 서로 다른 포트(5173, 8080, 8000) 간의 안전한 데이터 통신 구축
- **Docker 기반 AI 환경 구축**: 라이브러리 의존성이 복잡한 AI 엔진의 배포 편의성 증대
- **음성 데이터 정규화**: FFmpeg를 활용한 다양한 오디오 포맷의 표준화 작업 처리

---

## 👥 팀원
- **Full-Stack & AI Engine**: 배석현 (bjh49)
