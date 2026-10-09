# ✈️ AeroAssist AI — RAG-Based Aircraft Maintenance Assistant

An AI-powered aviation assistant that uses **Retrieval-Augmented Generation (RAG)** to answer questions about aircraft maintenance using relevant information retrieved from aviation maintenance documents.

## 📌 Project Overview

Aviation maintenance requires accurate access to technical documentation. Finding relevant information across lengthy handbooks can be time-consuming.

**AeroAssist AI** combines document retrieval with a Large Language Model (LLM) to help users find relevant information from aircraft maintenance handbooks and generate context-aware responses.

Instead of relying only on the model's general knowledge, the system retrieves relevant document passages and uses them as context when generating answers.

## 🎯 Objectives

* Make aircraft maintenance documentation easier to search.
* Retrieve relevant passages from technical aviation documents.
* Generate contextual answers using Google's Gemini model.
* Reduce the time needed to locate relevant handbook information.
* Demonstrate the practical application of RAG in aviation documentation.

## ⚙️ Technologies Used

* **Python** — application logic
* **Google Gemini API** — language model for answer generation
* **FAISS** — vector similarity search
* **Embeddings** — represent document chunks as searchable vectors
* **Streamlit** — interactive web application
* **Pickle** — storage and loading of document metadata

## 🧠 How It Works

The application follows a Retrieval-Augmented Generation pipeline:

1. **Document preparation** — aviation maintenance handbook content is processed into smaller text chunks.
2. **Embedding generation** — chunks are converted into vector representations.
3. **Vector indexing** — embeddings are stored in a FAISS index for similarity-based retrieval.
4. **User query** — the user asks a question through the Streamlit interface.
5. **Context retrieval** — relevant document chunks are retrieved from the vector index.
6. **Answer generation** — Gemini uses the retrieved context to formulate a response.
7. **Response display** — the answer is presented through the interactive application.

## 🏗️ Architecture

```text
Aviation Maintenance Handbooks
             ↓
      Text Processing
             ↓
       Text Chunking
             ↓
     Embedding Generation
             ↓
       FAISS Vector Index
             ↓
        User Question
             ↓
      Similarity Search
             ↓
   Retrieved Document Context
             ↓
       Gemini LLM API
             ↓
   Context-Aware Answer
             ↓
      Streamlit Interface
```

## ✨ Key Features

* **Natural-language queries:** Ask questions about aircraft maintenance documentation in everyday language.
* **Semantic retrieval:** Retrieve relevant passages based on meaning rather than exact keyword matches.
* **Context-aware responses:** Generate answers using retrieved handbook content.
* **Interactive interface:** Access the assistant through a Streamlit web application.
* **Vector-based search:** Use FAISS for efficient similarity search across document embeddings.

*Features should be adjusted to match the current implementation.*

## 🛠️ Project Structure

```text
AeroAssist-AI-RAG/
├── app.py
├── requirements.txt
├── aeroassist_index.faiss
├── metadata.pkl
└── .gitignore
```

* `app.py` — Streamlit application and RAG workflow.
* `requirements.txt` — Python dependencies.
* `aeroassist_index.faiss` — precomputed vector index.
* `metadata.pkl` — associated document metadata.
* `.gitignore` — excludes local environments and sensitive configuration files.

## 🚀 Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/Minal-2007/AeroAssist-AI-RAG.git
cd AeroAssist-AI-RAG
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it on Windows:

```bash
.venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

### 4. Configure the Gemini API key

Create a file named `.streamlit/secrets.toml` and add:

```toml
GEMINI_API_KEY = "YOUR_GEMINI_API_KEY"
```

Replace the placeholder with your own API key. **Never commit this file or expose your API key in source code.**

### 5. Start the application

```bash
streamlit run app.py
```

Open the local URL displayed in your terminal.

## 🌐 Live Demo

**Streamlit App:** [Add your deployed AeroAssist AI URL here]

**GitHub Repository:** [AeroAssist-AI-RAG](https://github.com/Minal-2007/AeroAssist-AI-RAG)

## 🔍 Why RAG?

A standard LLM generates responses using its learned knowledge, which may not contain the specific information required from a particular handbook.

RAG adds a retrieval step that supplies relevant document passages to the model before it generates an answer. This makes the responses more grounded in the selected documentation, although incorrect or incomplete answers remain possible.

## 🔭 Future Improvements

* Display source passages and document references alongside answers.
* Improve retrieval quality through chunking and embedding experiments.
* Add reranking to prioritize the most relevant retrieved passages.
* Support additional maintenance handbooks and document formats.
* Add retrieval evaluation and answer-quality testing.
* Improve handling of questions that cannot be answered from the available documents.

## ⚠️ Disclaimer

AeroAssist AI is an educational AI project for exploring aviation-document retrieval and question answering. Its responses must not be treated as approved maintenance instructions, and the system is not a substitute for current, applicable, manufacturer-approved maintenance documentation or qualified aviation maintenance personnel.

## 👩‍💻 Author

**Minal Gunasekaran**
Mechatronics Engineering | AI/ML | Robotics

* GitHub: [Minal-2007](https://github.com/Minal-2007)

## 📄 License

Add a license file if you intend to distribute the project for reuse.
