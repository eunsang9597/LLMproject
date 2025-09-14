# MorningBrief - AI-Powered Stock Market News Briefing System

## 📋 프로젝트 개요

MorningBrief는 미국 주식 시장 뉴스와 최신 정보를 수집하여 AI를 통해 요약하고, 사용자에게 필요한 정보를 빠르게 전달하는 시스템입니다. 웹 크롤링, LLM(Large Language Model) 활용, 그리고 웹 인터페이스를 통한 사용자 경험을 제공합니다.

## 🏗️ 프로젝트 구조

```
MorningBrief/
├── TodayStock/                    # 주식 뉴스 수집 및 분석 모듈
│   ├── MorningBrief.ipynb        # 메인 Jupyter 노트북 (Gradio 데모)
│   ├── chg_promt.txt             # ChatGPT 프롬프트 템플릿
│   ├── LLMsearch.txt             # LLM 검색 쿼리 템플릿
│   ├── summary.txt               # 수집된 뉴스 요약 데이터
│   └── README.md                 # TodayStock 모듈 설명
├── web/                          # Reflex 기반 웹 애플리케이션
│   ├── web.py                    # 메인 웹 앱 설정
│   ├── components/               # UI 컴포넌트
│   │   ├── navbar.py            # 네비게이션 바
│   │   ├── sidebar.py           # 사이드바
│   │   └── utils.py             # 유틸리티 함수
│   ├── pages/                   # 페이지 라우팅
│   │   ├── pages.py             # 페이지 정의
│   │   ├── common.py            # 공통 페이지 로직
│   │   └── utils.py             # 페이지 유틸리티
│   ├── styles.py                # 스타일 정의
│   └── templates/               # 템플릿 관리
├── aws/                         # AWS SageMaker JumpStart 예제
│   └── jumpstart/               # Upstage 모델 데모 노트북들
│       ├── 01_ocr.ipynb         # OCR 기능 데모
│       ├── 02_document_parse.ipynb
│       ├── 03_solar_mini_chat.ipynb
│       ├── 04_solar_mini_chat_client.ipynb
│       ├── 05_solar_mini_chat_ja.ipynb
│       ├── 06_solar_embedding_large.ipynb
│       ├── 07_solar_pro_preview.ipynb
│       ├── 08_solar_pro_preview_client.ipynb
│       ├── 09_solar_docvision_preview.ipynb
│       └── README.md
├── assets/                      # 정적 자산
│   ├── favicon.ico
│   ├── upstage_black.png
│   └── upstage_white.png
├── requirements.txt             # Python 의존성
├── rxconfig.py                 # Reflex 설정
└── LICENSE                     # 라이선스
```

## 🚀 주요 기능

### 1. 데이터 수집 (TodayStock)
- **웹 크롤링**: CNBC 등 미국 비즈니스 뉴스 사이트에서 주식 관련 뉴스 수집
- **Selenium 활용**: 동적 웹 페이지에서 뉴스 기사 자동 수집
- **대상 주식**: Microsoft (MSFT), NVIDIA (NVDA), Tesla (TSLA)
- **LLM 검색**: ChatGPT를 통한 최신 주식 정보 수집

### 2. AI 기반 요약 (LLM Integration)
- **Upstage Solar 모델**: LangChain과 연동하여 뉴스 요약
- **프롬프트 엔지니어링**: 3줄 요약을 위한 최적화된 프롬프트
- **실시간 처리**: 수집된 뉴스를 즉시 요약하여 제공

### 3. 웹 인터페이스
- **Gradio 데모**: Jupyter 노트북 기반의 간단한 채팅 인터페이스
- **Reflex 웹앱**: 고급 웹 애플리케이션 (개발 중)
- **반응형 디자인**: 다양한 디바이스에서 최적화된 사용자 경험

### 4. AWS SageMaker 통합
- **Upstage 모델**: AWS Marketplace의 Upstage 모델 활용 예제
- **OCR 기능**: 문서 이미지에서 텍스트 추출
- **다국어 지원**: 한국어, 영어 등 다국어 처리

## 🛠️ 기술 스택

### Backend
- **Python 3.12+**
- **LangChain**: LLM 프레임워크
- **Upstage Solar**: 한국어 LLM
- **Selenium**: 웹 크롤링
- **BeautifulSoup4**: HTML 파싱
- **Requests**: HTTP 요청

### Frontend
- **Reflex**: Python 기반 웹 프레임워크
- **Gradio**: 빠른 ML 데모 인터페이스
- **Plotly**: 데이터 시각화

### Cloud & Infrastructure
- **AWS SageMaker**: ML 모델 배포
- **AWS JumpStart**: 사전 훈련된 모델 활용

## 📦 설치 및 실행

### 1. 의존성 설치
```bash
pip install -r requirements.txt
```

### 2. 환경 변수 설정
```bash
# .env 파일 생성
echo "UPSTAGE_API_KEY=your_api_key_here" > .env
```

### 3. Gradio 데모 실행
```bash
cd TodayStock
jupyter notebook MorningBrief.ipynb
# 또는
python -c "import gradio as gr; exec(open('MorningBrief.ipynb').read())"
```

### 4. Reflex 웹앱 실행
```bash
reflex run
```

## 📊 사용법

### 1. 뉴스 수집
- `MorningBrief.ipynb`를 실행하여 자동으로 최신 주식 뉴스 수집
- CNBC에서 MSFT, NVDA, TSLA 관련 뉴스 자동 크롤링
- ChatGPT를 통한 추가 정보 수집

### 2. AI 요약
- 수집된 뉴스를 Upstage Solar 모델로 3줄 요약
- 실시간 채팅 인터페이스를 통한 추가 질문 가능

### 3. 웹 인터페이스
- Gradio: `http://127.0.0.1:7860`
- Reflex: `http://localhost:3000`

## 🔧 설정 및 커스터마이징

### 뉴스 소스 추가
```python
# TodayStock/MorningBrief.ipynb에서 수정
def get_articles(url):
    # 새로운 뉴스 소스 URL 추가
    pass
```

### 프롬프트 수정
```python
# TodayStock/MorningBrief.ipynb에서 수정
prompt_template = PromptTemplate.from_template(
    """
    사용자 정의 프롬프트 템플릿
    TEXT: {text}
    """
)
```

### 웹 UI 커스터마이징
```python
# web/styles.py에서 스타일 수정
# web/components/에서 컴포넌트 수정
```

## 📈 데이터 흐름

1. **수집**: Selenium으로 CNBC 뉴스 크롤링
2. **저장**: `summary.txt`에 원본 데이터 저장
3. **처리**: LangChain + Upstage Solar로 요약
4. **제공**: Gradio/Reflex 인터페이스로 사용자에게 전달

## 🤝 기여하기

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다. 자세한 내용은 [LICENSE](LICENSE) 파일을 참조하세요.

## 🔗 관련 링크

- [Upstage Solar 모델](https://upstage.ai/)
- [LangChain 문서](https://python.langchain.com/)
- [Reflex 문서](https://reflex.dev/)
- [Gradio 문서](https://gradio.app/)
- [AWS SageMaker JumpStart](https://aws.amazon.com/sagemaker/jumpstart/)
---

**MorningBrief** - AI로 만드는 스마트한 주식 뉴스 브리핑 시스템 🚀
