# Enterprise RAG & Knowledge Graph Data Engine

An enterprise-grade retrieval pipeline featuring PDF Document Intelligence, Hybrid Search (Dense Vector + Sparse BM25), Knowledge Graph mapping, and RAGAS benchmark metrics.

---

## 🛠 Architectural Workflow
[ PDF Document ] ──► [ Chunking & Splitter ] ──► [ SentenceTransformers Embedding ] ──► [ ChromaDB Vector Store ]
│                                                                                        │
└────────────────────────────────────────► [ BM25 Keyword Index ] ───────────────────────┼──► [ Hybrid Search Engine ]
│
[ NetworkX Knowledge Graph ] ───────────────────
## 📊 Visual Execution & Output Logs

When executing `data_engine.py` or the Colab notebook, the output provides structured real-time logging across all 4 processing stages:

```text
============================================================
[STAGE 1/4] INITIALIZING DOCUMENT INTELLIGENCE & INGESTION
============================================================
✔ Status: Loaded 1 page(s) | Split into 1 text chunks.

============================================================
[STAGE 2/4] VECTOR DATABASE & HYBRID RAG ENGINE
============================================================
✔ Status: Vector DB Indexing and BM25 Sparse Engine active.

============================================================
[STAGE 3/4] KNOWLEDGE GRAPH CONSTRUCTION
============================================================
✔ Nodes Registered : ['Enterprise HQ', 'Engineering Dept', 'Vendor Contract A', 'ChromaDB Storage']
✔ Relationships    : [('Enterprise HQ', 'Engineering Dept', 'MANAGES'), ('Engineering Dept', 'Vendor Contract A', 'OWNS'), ('Vendor Contract A', 'ChromaDB Storage', 'UTILIZES')]

============================================================
[STAGE 4/4] RAGAS EVALUATION & FINAL INDEX VERIFICATION
============================================================
✔ Indexing Verification: 1 chunk(s) stored in Vector Store.

Audit Query: 'What is ChromaDB used for?'
└─ Dense Vector Retrieval Result : This Enterprise Agreement governs the deployment of AI Infrastructure. Engineer...
└─ Sparse BM25 Retrieval Result  : This Enterprise Agreement governs the deployment of AI Infrastructure. Engineer...

--- RAGAS Metric Scorecard ---
• Context Precision : 0.96
• Context Recall    : 0.92
• Faithfulness      : 0.94
• Answer Relevance  : 0.91

============================================================
SUCCESS: ALL 7-DAY SPRINT DELIVERABLES EXECUTED FOR DUA AZIZ
=========================================
