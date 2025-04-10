# WIP: AI Agent for Proactive Supply Chain Disruption Management

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An AI Agent leveraging fine-tuned LLMs (Mistral-7B w/ PEFT) and LangGraph to proactively identify, assess, and suggest mitigations for supply chain disruptions, tailored to specific client needs. Includes MLOps integration using Vertex AI and MLflow.

**Problem:** Managing complex global supply chains involves constant risk of disruptions (weather, geopolitical events, port closures, etc.). Reacting to these events is costly and impacts client satisfaction.

**Solution:** This project implements a proactive AI agent that:
1.  Ingests real-time event data (news, weather, alerts).
2.  Filters relevant events.
3.  Uses a **client-specific fine-tuned LLM** to assess the potential impact on specific supply chain routes, considering client SLAs and product sensitivities (e.g., temperature for Pharma Companies).
4.  Employs an ML model (XGBoost) and LLM reasoning to forecast disruption impact (delays, costs).
5.  Suggests context-aware mitigation actions using an LLM enhanced with Retrieval-Augmented Generation (RAG) on Standard Operating Procedures (SOPs) and historical incident data.
6.  Leverages **LangGraph** to create a robust, stateful agent workflow with conditional logic based on severity and client type.
7.  Integrates with **MLOps** practices using Google Cloud Vertex AI (Pipelines, Training, Endpoints) and MLflow for experiment tracking and model management.

**Differentiation:** The key differentiator is the **client-specific fine-tuning** of the core LLM. Instead of generic risk assessment, the agent understands the unique network topology, contracts, and vulnerabilities of clients like Shell or Pfizer, providing highly relevant and actionable insights.

## Key Features

*   Proactive Disruption Identification
*   Client-Specific Impact Assessment (Fine-tuned LLM)
*   Multi-modal Impact Forecasting (ML + LLM)
*   RAG-Enhanced Mitigation Suggestions (SOPs, History)
*   Stateful Agent Workflow (LangGraph)
*   Robust MLOps pipeline on Vertex AI
*   Experiment Tracking & Model Registry (MLflow)
*   API for integration (FastAPI)

## Tech Stack

*   **Orchestration:** Langchain, LangGraph
*   **LLMs:** Mistral-7B (Base Model), Hugging Face Transformers, PEFT (LoRA)
*   **ML:** PyTorch (potentially underlying Transformers), Scikit-learn, XGBoost
*   **Cloud Platform:** Google Cloud Platform (GCP)
    *   **MLOps:** Vertex AI (Pipelines, Custom Training, Endpoints, Prediction)
    *   **Data:** BigQuery, Cloud Storage, Pub/Sub
    *   **Compute:** Google Kubernetes Engine (GKE) or Cloud Run
    *   **Vector DB:** Vertex AI Vector Search or compatible alternative (e.g., Pinecone, ChromaDB self-hosted)
*   **Experiment Tracking:** MLflow
*   **API:** FastAPI, Uvicorn
*   **Containerization:** Docker
*   **Monitoring:** Prometheus, Grafana (via Cloud Monitoring adapters)
*   **Infra-as-Code (Optional):** Terraform
*   **Language:** Python
