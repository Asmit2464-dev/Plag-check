# 🔍 PlagioCheck — Full-Stack AI & Web Plagiarism Detection System

PlagioCheck is a full-stack, microservice-based text analysis platform that scans text, code, and documents for plagiarized content across the live internet, and evaluates text for AI-generated patterns (ChatGPT, Claude, Gemini).

---

## ✨ Features & Capabilities

- 🌐 **Live Web Plagiarism Engine**:
  - Crawls and searches the live internet using the **Tavily AI Search Engine**.
  - Ranks matching sources and returns direct **source URLs**, page titles, and similarity percentages.
  - Sentence-level granularity: Highlights exact matching sentences with their corresponding web sources.

- 🤖 **AI Content Probability Detector**:
  - Evaluates text using 4 NLP heuristics to detect LLM-authored text:
    1. **Sentence Burstiness & Uniformity**: Analyzes sentence length variance.
    2. **Perplexity Proxy**: Measures lexical diversity and unique-to-total word ratios.
    3. **AI Keyword Scanner**: Identifies common LLM buzzwords and phrase structures.
    4. **Transition Word Density**: Evaluates connective word frequencies.

- 💻 **Programming Code Similarity Detector**:
  - Automatically identifies code vs. natural language.
  - Sanitizes comments (`# ...`) and string literals (`"..."`) to focus on structural code logic.
  - Computes structural similarity using TF-IDF vectorization.

- 📄 **Multi-Format Document Parsing**:
  - Upload `.pdf`, `.docx`, and `.txt` files.
  - Parsed directly on the client side using `pdfjs-dist` (PDFs) and `mammoth` (Word documents).

- 🎙️ **Voice-to-Text Input**:
  - Dictate text or reference passages using browser-native **Web Speech API** (`SpeechRecognition`).

- 📊 **Visual Analytics & PDF Export**:
  - Interactive **Chart.js** doughnut charts showing originality vs. similarity breakdowns.
  - One-click downloadable **PDF scan reports** generated via `jspdf`.

- 🛡️ **Authentication & History (Optional)**:
  - JWT-based authentication with `bcryptjs` password encryption.
  - Persistent scan history stored in MongoDB.
  - Graceful fallback: Plagiarism and AI scans work 100% even without MongoDB connected.

---

## 🏗️ System Architecture

PlagioCheck uses a **3-tier decoupled microservice architecture**:
