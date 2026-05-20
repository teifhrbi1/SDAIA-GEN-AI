# Contract Analyst AI: Intelligent Legal Review System ⚖️🤖

## Overview
Contract Analyst AI is an automated, high-performance system engineered to streamline contract reviews, extract critical entities, and verify compliance against corporate policies. Leveraging Generative AI and Retrieval-Augmented Generation (RAG), this system acts as a multi-agent legal assistant to ensure contracts align with local regulations and corporate standards.

## Key Features & Architecture
- **Entity Extraction:** Utilizes `Pydantic` to enforce structured JSON outputs (Vendor Name, Total Amount, Risk Flags, Supporting Policies) directly from raw legal text.
- **RAG Grounding:** Integrates `ChromaDB` and `SentenceTransformers` (`all-MiniLM-L6-v2`) to embed and retrieve relevant clauses from the policy database (e.g., SDAIA-Corp Vendor Policy).
- **Multi-Agent Logic:** Decouples the extraction and review processes into distinct operational agents for higher accuracy and modularity.
- **Mathematical Evaluation:** Incorporates the `DeepEval` framework (specifically `FaithfulnessMetric`) to mathematically score the LLM's adherence to the retrieved context, effectively preventing hallucinations.
- **System Resilience (Graceful Degradation):** Features a robust fallback mechanism to handle API rate limits (HTTP 429) seamlessly. The system transitions into a simulated demonstration mode when quotas are exhausted, ensuring uninterrupted operation during live presentations.

## Tech Stack
- **Language:** Python 3.12
- **LLM:** Google Gemini 2.0 Flash
- **Vector Database:** ChromaDB
- **Data Validation:** Pydantic
- **Evaluation Framework:** DeepEval

## Datasets
- `Company_Policy_Base (For RAG DB).txt`: Contains strict corporate compliance rules regarding payment terms (Net 30), liability caps, KSA governing law, and local data hosting requirements.
- `Test_Contracts (For testing the agent).json`: Contains sample MSA and licensing agreements to test the system's ability to flag violations.

## Installation & Usage
1. Clone the repository and navigate to the project directory:
   ```bash
   git clone [https://github.com/teifhrbi1/SDAIA-GEN-AI.git](https://github.com/teifhrbi1/SDAIA-GEN-AI.git)
   cd SDAIA-GEN-AI
