# LLM 서비스 개발 실습

모두의연구소 재직자 LLM 서비스 과정 6기 실습 저장소입니다.

## 커리큘럼

| 주차 | 주제 | 핵심 기술 |
|------|------|-----------|
| Weekend 1 | API & Chain | OpenAI API 직접 호출, LangChain LCEL 체인, 키워드 기반 FAQ 검색 |
| Weekend 2 | RAG Pipeline | FAISS 벡터 스토어, 임베딩 기반 시맨틱 검색, RAG 파이프라인 |
| Weekend 3 | Memory & Deploy | Few-shot, Chain-of-Thought, 대화 메모리, Gradio UI 배포 |

## 기술 스택

- **LLM**: OpenAI GPT-4o-mini (`langchain-openai`)
- **Embeddings**: OpenAI text-embedding-3-small
- **Vector Store**: FAISS (`faiss-cpu`)
- **Framework**: LangChain (LCEL 패턴)
- **UI**: Gradio

## 로컬 환경 설정

### 1. 저장소 클론

```bash
git clone https://github.com/rmaomina/llm_service_modu6.git
cd llm_service_modu6
```

### 2. 가상환경 생성 (권장)

```bash
python3 -m venv venv
source venv/bin/activate
```

### 3. 패키지 설치

```bash
pip install openai langchain langchain-openai langchain-community faiss-cpu python-dotenv gradio numpy
```

### 4. OpenAI API 키 설정

프로젝트 루트에 `.env` 파일을 생성하고 API 키를 입력합니다.

```
OPENAI_API_KEY=sk-proj-...
```

### 5. Jupyter Notebook 실행

```bash
jupyter notebook
```

브라우저에서 `http://localhost:8888`이 자동으로 열립니다.  
원하는 `.ipynb` 파일을 선택하여 실습을 진행하세요.

> **Google Colab 사용 시**: 각 notebook 상단의 Colab 설정 셀 주석을 해제하여 사용합니다.

## 프로젝트 구조

```
├── p1_weekend1_api_and_chain_0314.ipynb          # Weekend 1 실습 (템플릿)
├── p1_weekend2_rag_pipeline_0321.ipynb            # Weekend 2 실습 (템플릿)
├── p1_weekend3_memory_and_deploy_260328.ipynb     # Weekend 3 실습 (템플릿)
├── *_solution.ipynb                               # 풀이 파일
├── *_김민아.ipynb                                  # 개인 실습 파일
├── weekend1_api_and_chain/                        # 1주차 일일 학습 노트북
├── weekend2_token_embedding_vector_rag/            # 2주차 일일 학습 노트북
├── weekend3_memory_prompt_engineering/             # 3주차 일일 학습 노트북
└── llm_260000_template.ipynb                      # Colab 환경 템플릿
```
