# ConversAI-SQL-Agent
💬 ConversAI: A multi-agent SQL Intelligence System that lets users query e-commerce data using natural language — powered by RAG, ChromaDB, and Gemini

How to Run

1️⃣ Download the datasets
Archive datasets: https://drive.google.com/drive/folders/1JSgeO4nyG8QCO41UVWpg4yq4QBlk4lA_?usp=drive_link
Chroma DB datasets:https://drive.google.com/drive/folders/1x9lGVSrZ64G-wtJSJggEif49OfX7-D__?usp=drive_link


2️⃣ Download the ConversAI-SQL-Agent repository

Get finalwithui.ipynb
 and finalwithui.py

3️⃣ Running the code

If using Python script (.py):
Open finalwithui.py
Add your API key where indicated in the script
Run the entire file at onc
<img width="1098" height="676" alt="image" src="https://github.com/user-attachments/assets/b5797171-3129-41bb-bedc-880ddf1fa9a4" />

If using Jupyter Notebook (.ipynb):
Open finalwithui.ipynb
Add your API key where indicated in the script
Run the notebook cell by cell




Architecture, Design Decisions & Future Work

Architecture & Design Decisions

Multi-Agent System: The project uses a modular architecture with specialized agents — SQL Agent, RAG Agent, PLOT Agent, Voice Agent, Web Agent, and a Router — each responsible for a different aspect of user queries. This separation ensures scalability and maintainability.

SQL Agent: Handles structured queries over eight related tables. Gemini 2.0 AI generation is used for flexibility, with a rule-based fallback for reliability.

RAG Agent & ChromaDB: Persistent vector store enables semantic search over unstructured text (e.g., 99,000+ customer reviews). BAAI/bge-m3 embeddings are used for fast, multilingual vectorization.

PLOT Agent: Automatically detects chart types and generates visualizations from SQL results without manual coding.

Voice Agent & Speech Recognition: Improves accessibility and provides natural interaction. Google Speech Recognition is primary; Sphinx offline fallback ensures reliability.

Router & Context Management: Acts as the “brain” to select agents, resolve context, and cache recent queries, enabling follow-up interactions like “plot that” or “show reviews for that product.”

Hybrid AI + Rule-Based Approach: Critical for speed, accuracy, and handling API limits. Structured queries rely on AI generation; common patterns fall back to pre-defined rules.

Other Details & Future Work

Context-Aware & Persistent Memory: Stores last SQL results, product IDs, category info, and recent query history to support conversational interactions.

Extensibility: New agents or knowledge sources can be added without affecting existing functionality.

Future Improvements:

Multi-language support for queries and responses

Query suggestions with auto-complete for faster interactions

Predictive analytics for sales trends

Real-time order streaming and monitoring

Fine-tuning domain-specific AI models for more accurate SQL generation using LoRA (Low-Rank Adaptation) to efficiently adapt pre-trained models without full retraining

Enhanced visualizations and interactive dashboards

Summary:
The design emphasizes modularity, reliability, and natural user interaction, balancing AI-generated insights with rule-based fallback. With additional time, the system could evolve into a full-fledged intelligent analytics assistant for e-commerce or other structured + unstructured datasets.
