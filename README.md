# LangChain WebBase Document Loader
[![LangChain](https://img.shields.io/badge/Framework-LangChain-green)](https://www.langchain.com/)
[![Python](https://img.shields.io/badge/Python-3.9%2B-blue)](https://www.python.org/)
[![BeautifulSoup](https://img.shields.io/badge/Parsing-BeautifulSoup4-orange)](https://www.crummy.com/software/BeautifulSoup/)

## 🏗️ Project Overview
This repository focuses on **Dynamic Data Ingestion**. While loading local PDFs is essential, modern Retrieval-Augmented Generation (RAG) systems often need to answer questions based on live, frequently updated information (like a company's FAQ page, documentation, or news articles). This project demonstrates how to use LangChain's **`WebBaseLoader`** to scrape websites and convert HTML into clean, structured `Document` objects that an LLM can easily understand.

---

## 🛠️ Key Technical Implementations

### 1. HTML to Text Transformation
* **`WebBaseLoader` Integration:** Bypassing manual `requests` calls by utilizing LangChain's built-in loader to fetch and decode web pages.
* **DOM Parsing:** Leveraging `beautifulsoup4` under the hood to strip out HTML tags, scripts, and CSS, leaving only the semantically relevant human-readable text.

### 2. Targeted Extraction (Token Optimization)
* **`SoupStrainer` Implementation:** Web pages are full of noise (navbars, footers, sidebars) which waste LLM context window space. This project demonstrates how to target specific HTML classes or IDs (e.g., `<article>` or `<div class="main-content">`) to extract *only* the relevant data, optimizing token usage and reducing costs.

### 3. Metadata Preservation
* **Source Tracking:** Automatically capturing the `source` (URL), `title`, and `description` tags from the webpage's `<head>`. This ensures the AI can provide clickable citations to the user, proving the provenance of its answers.

---

## 💻 Tech Stack
* **Language:** Python 3.9+
* **Framework:** LangChain Community (`langchain-community`)
* **Dependencies:** `beautifulsoup4`
* **Environment:** `python-dotenv`

---

## 🚀 Getting Started

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/your-username/langchain-webbase-loader-scraping.git](https://github.com/your-username/langchain-webbase-loader-scraping.git)

2. **Install Dependencies:**
   ```bash
   pip install -U langchain-community beautifulsoup4 python-dotenv

3. **Run the Implementation:**
  ```bash
  python webbase_loader.py   
