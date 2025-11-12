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

**If using Python script (.py)**:

Open finalwithui.py
Installations in command line :
# System dependencies (Linux only; skip if on Windows)
sudo apt-get install -y portaudio19-dev python3-pyaudio
**Windows:**  
  Install PyAudio from pre-built wheel: https://www.lfd.uci.edu/~gohlke/pythonlibs/#pyaudio  
  Then run:  
  pip install path\to\PyAudio‑<version>.whl

# Python packages
pip install SpeechRecognition pyaudio
pip install gradio
pip install langchain==0.2.16 langchain-community==0.2.16 google-generativeai==0.7.2 chromadb sentence-transformers
pip install transformers==4.44.2 huggingface-hub==0.23.5 sentence-transformers==2.6.1
pip install --upgrade pip numpy

Add your google  API key where indicated in the script
<img width="869" height="609" alt="image" src="https://github.com/user-attachments/assets/554cd349-a0ec-4c5f-bd5c-a6d126496d05" />
Update your dataset path also as indicated:
<img width="781" height="200" alt="image" src="https://github.com/user-attachments/assets/c627356a-921e-4066-a23f-3e6d9e4e4d70" />
<img width="782" height="230" alt="image" src="https://github.com/user-attachments/assets/a64615bd-9052-4f45-a411-c71e010d76e6" />

Run the script using:
**python finalwithui.py**

**If using Jupyter Notebook (.ipynb):**
Open finalwithui.ipynb in google colab
load the datasets to your drive 
Add your google API key where indicated in the script
<img width="966" height="288" alt="image" src="https://github.com/user-attachments/assets/470625c5-debf-4e91-a3f1-b0e263f27f73" />
Update your dataset path also as indicated:
<img width="971" height="151" alt="image" src="https://github.com/user-attachments/assets/7d05d3fc-9107-4aa6-b1cf-991985550f94" />
<img width="886" height="162" alt="image" src="https://github.com/user-attachments/assets/cc928c9e-b221-438f-884e-9cce8f7b5bc9" />
if needed :
!pip install gradio
Run the notebook cell by cell


**Architecture, Design Decisions & Future Work**

**Architecture & Design Decisions**

Multi-Agent System: The project uses a modular architecture with specialized agents — SQL Agent, RAG Agent, PLOT Agent, Voice Agent, Web Agent, and a Router — each responsible for a different aspect of user queries. This separation ensures scalability and maintainability.

SQL Agent: Handles structured queries over eight related tables. Gemini 2.0 AI generation is used for flexibility, with a rule-based fallback for reliability.

RAG Agent & ChromaDB: Persistent vector store enables semantic search over unstructured text (e.g., 99,000+ customer reviews). BAAI/bge-m3 embeddings are used for fast, multilingual vectorization.

PLOT Agent: Automatically detects chart types and generates visualizations from SQL results without manual coding.

Voice Agent & Speech Recognition: Improves accessibility and provides natural interaction. Google Speech Recognition is primary; Sphinx offline fallback ensures reliability.

Router & Context Management: Acts as the “brain” to select agents, resolve context, and cache recent queries, enabling follow-up interactions like “plot that” or “show reviews for that product.”

Hybrid AI + Rule-Based Approach: Critical for speed, accuracy, and handling API limits. Structured queries rely on AI generation; common patterns fall back to pre-defined rules.

**Other Details & Future Work**

Context-Aware & Persistent Memory: Stores last SQL results, product IDs, category info, and recent query history to support conversational interactions.

Extensibility: New agents or knowledge sources can be added without affecting existing functionality.

**Future Improvements:**

Multi-language support for queries and responses

Query suggestions with auto-complete for faster interactions

Predictive analytics for sales trends

Real-time order streaming and monitoring

Fine-tuning domain-specific AI models for more accurate SQL generation using LoRA (Low-Rank Adaptation) to efficiently adapt pre-trained models without full retraining

Enhanced visualizations and interactive dashboards

**Summary:**
The design emphasizes modularity, reliability, and natural user interaction, balancing AI-generated insights with rule-based fallback. With additional time, the system could evolve into a full-fledged intelligent analytics assistant for e-commerce or other structured + unstructured datasets.
