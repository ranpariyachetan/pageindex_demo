# PageIndex Demo

## 1. Description and Overview
This repository demonstrates a vectorless RAG workflow on a PDF using PageIndex for document structure retrieval and OpenAI for reasoning and answer generation.

## 2. What Is Included
- `src/pageindex_demo.ipynb`: End-to-end notebook demo.
- `src/data/2603.15031.pdf`: Sample PDF used by the notebook.
- `.env`: Local environment variables for API keys.

## 3. Setup and Dependency Installation
1. Use Python 3.10+.
2. Create and activate a virtual environment.
3. Install required packages:
   - `pip install pageindex openai python-dotenv jupyter ipykernel`
4. Open and run `src/pageindex_demo.ipynb` in VS Code or Jupyter.

## 4. Secrets and API Keys
You need two keys:
- `PAGEINDEX_API_KEY` from your PageIndex account/dashboard.
- `OPENAI_API_KEY` from your OpenAI account/dashboard.

Add them to `.env` at repository root:
- `PAGEINDEX_API_KEY=...`
- `OPENAI_API_KEY=...`

Keep `.env` local only. Do not share or commit real keys.

## 5. Major Code Sections
- Client setup and environment loading.
- PDF submission and document processing status polling.
- Tree retrieval, printing, and node counting.
- LLM tree search (`llm_tree_search`) to select relevant nodes.
- Grounded answer generation (`generate_answer`) from retrieved nodes.
- End-to-end pipeline (`vectorless_rag`) plus direct PageIndex chat call and streaming MCP example.

## 6. Run Instructions and What to Observe
Run notebook cells in order.

Expected flow/output:
- PDF upload confirmation with `doc_id`.
- Status updates until processing is `completed`.
- Printed tree structure and total node count.
- Retrieved relevant node IDs for the query.
- Final concise answer with section/page grounding.
- Optional final streaming cell shows reasoning, tool-use events, and answer text.
