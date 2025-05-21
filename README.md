# face-recognition-webapp
안면인식 웹 애플리케이션
# 안면인식 웹 애플리케이션 (Face Recognition Web App)

이 프로젝트는 **MediaPipe**와 **Flask**, **React**, **ngrok**을 활용하여 안면을 등록하고 인식하는 기능을 제공하는 웹 애플리케이션입니다. Google Colab에서 실행 가능하며, 카메라를 통해 얼굴을 등록하고 실시간으로 인식할 수 있습니다.

## 주요 기능

- 전/후면 카메라 선택 및 실시간 영상 스트리밍
- 얼굴 등록 (이름과 함께 저장)
- 얼굴 인식 및 일치 결과 시각화
- 유사도 기반 매칭 알고리즘
- MediaPipe 기반 특징점 추출
- ngrok을 통한 외부 접속 가능 URL 생성

---

## 기술 스택

- **Frontend**: HTML, React (CDN + Babel)
- **Backend**: Python, Flask, Flask-CORS
- **AI/ML**: Google MediaPipe (`face_detection`, `face_mesh`)
- **서버 실행 도구**: pyngrok
- **환경**: Google Colab

---

## 폴더 구조
├── app.py               # Flask 백엔드 서버

├── run_server.py        # ngrok 실행 스크립트

├── face_data/           # 등록된 얼굴 특징점 저장

├── www/

│   └── index.html       # React 기반 프론트엔드

---

## 설치 및 실행 (Google Colab 기준)

1. 패키지 설치

```bash
!pip install flask flask-cors mediapipe opencv-python-headless pyngrok
from pyngrok import ngrok
ngrok.set_auth_token("YOUR_NGROK_TOKEN")
!python run_server.py
