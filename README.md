## Ticket Support Agent

A comprehensive ticket retrieval and analysis system powered by **RAG (Retrieval-Augmented Generation)** technology.

### Problem
In customer support, teams frequently encounter identical or highly relevant tickets that have already been resolved for other users. Traditional systems often rely on **keyword-based search**, which lacks semantic context. When an agent needs a resolution summary based on multiple past cases, it typically requires hours of manual research and analysis.

### Solution
This agent streamlines the process by allowing support teams to simply input a user query. Using a **RAG-based system**, the agent automatically:

* **Fetches** the $n$ most relevant historical tickets based on intent, not just keywords.
* **Analyzes** the data to synthesize a concise solution summary.
* **Responds** with actionable advice, backed by **cited original tickets** for transparency.

### Key Benefits
* **Intelligent Search:** Moves beyond keywords to understand the actual meaning of a support request.
* **AI-Powered Summarization:** Reduces "research debt" by condensing hours of manual review into seconds.
* **Cross-Domain Utility:** Delivers high-quality responses across technical, product, and general customer support categories.

## Tech Stack
* **Framework:** Python, FastAPI, LangChain
* **Vector DB:** ChromaDB
* **LLM:** OpenAI (GPT-4o + `text-embedding-ada-002`)
* **UI:** Streamlit

### Getting Started

#### Prerequisites

- Python 3.13+
- OpenAI API Key

#### Installation

1. Clone the repository:
```bash
git clone <repository-url>
cd ticket_retrieval_system
```

2. Install dependencies using uv:
```bash
uv sync
```

3. Create a `.env` file with your OpenAI API key:
```bash
cp .env.example .env
```

#### Data Setup

Place your support ticket files in the `data/` directory:
- `Technical Support_tickets.json` / `Technical Support_tickets.xml`
- `Product Support_tickets.json` / `Product Support_tickets.xml`
- `Customer Service_tickets.json` / `Customer Service_tickets.xml`

### Usage

### Streamlit UI (Recommended)

Launch the interactive web interface:

```bash
python main.py --ui
```

#### Command Line Interface

##### Initialize the system:
```bash
python main.py --init
```

##### Query from CLI:
```bash
python main.py --query "Queries are running slower than usual" --type technical --results 5
```