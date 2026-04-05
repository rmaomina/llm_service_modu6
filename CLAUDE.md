# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

모두의연구소 재직자 LLM 서비스 과정 6기 실습 저장소. Jupyter notebook 기반으로 주택청약 FAQ 챗봇을 점진적으로 구축하는 프로젝트.

## Project Structure

- **p1_weekend1**: OpenAI API 직접 호출 + LangChain LCEL 체인으로 키워드 기반 FAQ 검색 시스템 구축
- **p1_weekend2**: FAISS 벡터 스토어 + RAG 파이프라인으로 시맨틱 검색 업그레이드
- **260320_modu_수업(중간)**: 수업 중간 실습 (Document 로딩, FAISS, LCEL RAG 체인)
- 각 notebook은 10개 사이클(단계)로 구성되며, 빈 코드 셀을 채워나가는 형식

## Tech Stack

- **LLM**: OpenAI GPT-4o-mini (`langchain-openai`)
- **Embeddings**: OpenAI text-embedding-3-small
- **Vector Store**: FAISS (`langchain-community`, `faiss-cpu`)
- **Framework**: LangChain (LCEL 패턴: `prompt | llm | StrOutputParser()`)
- **UI**: Gradio (`gr.ChatInterface`)
- **Environment**: `.env` 파일에 `OPENAI_API_KEY` 설정 필요

## Setup

```bash
pip install openai langchain-openai langchain-community faiss-cpu python-dotenv gradio
```

Google Colab 사용 시 각 notebook 상단의 Colab 설정 셀 주석을 해제하여 사용.

## Key Patterns

- RAG 체인은 LCEL로 구성: `{"context": retriever | format_docs, "question": RunnablePassthrough()} | prompt | llm | StrOutputParser()`
- FAQ 데이터는 `SAMPLE_FAQ_DATA` 딕셔너리 리스트로 각 notebook에 인라인 정의됨
- FAISS 인덱스는 `save_local()` / `load_local(allow_dangerous_deserialization=True)`로 저장/로드
