# Skill-Ronin — AI-Powered Resume Builder

An intelligent resume analysis platform built on a microservices architecture. Skill-Ronin ingests, parses, and evaluates resumes using LLM-powered pipelines — helping users understand how their resume stacks up against real job requirements.

---

## Architecture Overview

The system is split into four independent services communicating through a central API gateway:

| Service | Responsibility |
|---|---|
| **User Service** | Authentication, profiles, JWT session management |
| **Resume Service** | Resume ingestion, parsing, and structured data extraction |
| **AI Service** | LLM-based evaluation, scoring, and RAG-powered retrieval |
| **Gateway + RAG** | Request routing, rate limiting, and vector search orchestration |

---

## Key Features

**Resume Parsing Pipeline**  
Combines Apache Tika for document extraction with regex heuristics and an LLM pass to produce clean, structured data from messy resume formats (PDF, DOCX, etc.).

**LLM Evaluation Engine**  
Powered by Groq's LLaMA inference API. Analyzes resume content against job descriptions, identifies skill gaps, and generates actionable feedback.

**RAG-Based Retrieval**  
Uses Qdrant as a vector store to retrieve semantically relevant job descriptions and benchmarks, grounding the LLM's evaluation in real-world context.

**Secure REST APIs**  
All service-to-service and client-facing communication is secured with JWT-based authentication and enforced at the gateway layer.

---

## Services

- **User Service** → [github.com/shivendra3535/User-Service](https://github.com/shivendra3535/User-Service)
- **Resume Service** → [github.com/shivendra3535/resume-service](https://github.com/shivendra3535/resume-service)
- **AI Service** → [github.com/shivendra3535/AI-Service](https://github.com/shivendra3535/AI-Service)
- **Gateway + RAG** → *(in progress)*

---

## Tech Stack

- **LLM Inference** — Groq (LLaMA)
- **Vector DB** — Qdrant
- **Document Parsing** — Apache Tika
- **Auth** — JWT
- **Architecture** — Microservices with REST APIs

---

## Status

> Gateway and RAG orchestration layer are actively under development.
