---

# 🤖 Agentic Plan Workbench: LLM-Powered Red Teaming for Function Calls

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python Version](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Framework: FastAPI](https://img.shields.io/badge/framework-FastAPI-green.svg)](https://fastapi.tiangolo.com/)

An interactive, multi-agent framework designed to help developers create, validate, and refine LLM function-calling plans. **You define the tools and the plan, and our LLM agents act as your expert red team**, providing critical feedback and generating an optimized "Golden Plan." This project serves as a demonstration of advanced competencies in AI engineering, multi-agent system design, and full-stack application development.

![Agentic Plan Workbench Screenshot](https://github.com/lewis-hue/Agentic-Plan-Workbench/blob/main/Agentic%20Workbench.png)

**Watch the** [**LIVE DEMO**](https://github.com/lewis-hue/Agentic-Plan-Workbench/blob/main/Agentic%20Plan%20Workbench-2.mp4)

---

## 🏛️ Core Competencies & Demonstrated Expertise

This project showcases a deep understanding of the principles and practices required to build robust, scalable, and intelligent AI systems. The expertise demonstrated spans across several key domains:

### 1. Multi-Agent System Design & Orchestration
The framework is architected as a collaborative multi-agent system, demonstrating a deep understanding of designing and orchestrating autonomous agents with specialized roles.

*   **Adversarial "Red Teaming" Architecture:** Implemented an advanced validation strategy where a `Critic` agent adversarially evaluates the output of a `Generator` (the user's plan). This "red team" approach is a sophisticated method for identifying blind spots and ensuring plan robustness, moving beyond simple validation.
*   **Stateful Workflow Orchestration:** The core logic manages the flow of data and state between the user's input, the `Critic's` analysis, and the LLM-powered plan revision. This demonstrates the ability to manage complex, multi-step AI workflows where the output of one agent becomes the input for another.
*   **Synergistic Agent Roles:** Designed agents with distinct, synergistic responsibilities. The `Critic` is specialized in analytical reasoning and flaw detection, while the revision step leverages a separate LLM prompt optimized for creative problem-solving and synthesis based on the `Critic's` structured feedback.

### 2. Advanced LLM Reasoning & Function Calling
The application's core functionality is centered on the nuanced and complex domain of LLM function calling, showcasing expertise in both its application and validation.

*   **Dynamic Schema Validation:** The system validates plans against user-provided JSON schemas at runtime. This demonstrates the ability to build flexible systems that can adapt to arbitrary tool definitions, a critical skill for creating general-purpose AI platforms.
*   **Semantic and Logical Flaw Detection:** The `Critic` agent is engineered to identify issues beyond simple syntactic errors. It detects:
    *   **Semantic Plausibility:** Arguments that are schema-compliant but contextually nonsensical.
    *   **Implicit Assumptions:** Plans that rely on information not available in the provided context.
    *   **Tool Hallucinations:** Use of tools or arguments that have been invented by the model.
    This showcases an expert ability to engineer prompts and logic that enforce higher-order reasoning.
*   **LLM-Powered Self-Correction:** The "Golden Plan" generation is a practical implementation of an LLM-based feedback loop. The system uses the structured critique from one LLM to prompt another LLM to perform a targeted, context-aware revision, demonstrating advanced prompt engineering for iterative refinement.

### 3. Synthetic Data Generation for AI/ML
The framework is strategically designed as a high-quality synthetic data generation engine, demonstrating a forward-thinking approach to the MLOps lifecycle.

*   **Structured Data for Fine-Tuning:** Every transaction generates a `(user_plan, critic_feedback, golden_plan)` triplet. This structured, high-quality data is invaluable for fine-tuning smaller, more efficient models to become expert function-calling agents, showcasing an understanding of the full model development pipeline.
*   **Standardized Data Formats:** The ability to export data in standard formats like JSONL demonstrates knowledge of data engineering best practices and the requirements for ML training workflows.

### 4. Robust Backend Architecture & API Design
The backend is built on modern, production-ready principles, showcasing strong software engineering fundamentals.

*   **Asynchronous Processing:** Built with FastAPI, which leverages Python's `asyncio` to handle concurrent I/O-bound operations (like LLM API calls) efficiently. This is a critical architectural choice for building scalable and responsive AI services.
*   **Data Integrity with Pydantic:** Utilized Pydantic models for all data structures, ensuring strict type safety, validation, and clear schema definition at the API boundary. This practice is essential for building reliable, bug-resistant systems.
*   **Modular, RESTful API:** Designed a clean, resource-oriented API that decouples frontend logic from backend services. Endpoints like `/api/analyze-plan` and `/api/update-tools` are modular and well-defined, facilitating easier maintenance and integration.

### 5. Interactive Frontend & Developer Experience (DevX)
The user interface is intentionally designed as a "workbench" for technical users, demonstrating a focus on creating effective tools for developers.

*   **Enhanced Developer Tooling:** Integrated the Monaco Editor (the engine behind VS Code) to provide a familiar, feature-rich editing experience with syntax highlighting and real-time JSON validation.
*   **Asynchronous UI for LLM Latency:** The frontend is designed to handle the inherent latency of LLM calls gracefully, providing clear loading states and updating asynchronously to maintain a responsive user experience.
*   **Complex Data Visualization:** The UI effectively translates the complex, structured output from the `Critic` agent into a human-readable format, using visual cues like color-coding, severity badges, and categorized critiques to provide instant, actionable insights.

---

## 📡 API Endpoints

The application exposes a full suite of API endpoints for programmatic integration:

| Endpoint | Method | Description |
|---|---|---|
| `/` | `GET` | Serves the main HTML interface (Agentic Plan Workbench). |
| `/health` | `GET` | Provides a health check of the application. |
| `/api/scenarios` | `GET` | Retrieves a list of pre-defined test scenarios. |
| `/api/analyze-plan`| `POST` | **Core Endpoint:** Analyzes a user-provided plan against user-provided tools. |
| `/api/update-tools`| `POST` | Updates the tool library with a new set of schemas. |
| `/api/run-workflow`| `POST` | Executes the complete multi-agent workflow for a given scenario.|
| `/api/training-data-stats`| `GET` | Returns statistics about the generated training data. |
| `/api/export-training-data/{format}` | `GET` | Exports training data in the specified format (e.g., jsonl).|

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](https://opensource.org/licenses/MIT) file for details.
