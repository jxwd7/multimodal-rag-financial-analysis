# Advanced RAG for Financial Analysis

### A Comparative Study of Multi-Modal vs. Text-Based Information Retrieval on 10-K Reports

This project develops and benchmarks four distinct Retrieval-Augmented Generation (RAG) systems to analyze complex financial documents, using Apple's 10-K report as a case study. The objective was to compare the trade-offs between accuracy, token usage (cost), and reliability, with a focus on a novel **Smart Multi-Modal RAG** approach.

This was a project for MAIB SEPT 2023 (AI Automation in Finance) by Ngo Pham Uyen Trang, Thuy Dong, and Jawwad Ahmed.

## 🎯 The Problem

Standard RAG systems often fail when information is contained within tables, charts, or complex layouts in a PDF, leading to hallucinations or incorrect data extraction. This project's "Smart MRAG" solves this by providing the LLM with visual context.

## 🔬 Architectures Compared

1.  **Smart MRAG (Hybrid):** A novel approach that retrieves a text chunk, then extracts an **image of the corresponding PDF page** to send to GPT-4o for visual context.
2.  **Text-Based RAG:** A standard baseline using LangChain and FAISS.
3.  **Pure Multi-Modal RAG:** Answers questions from full-page images only.
4.  **Sentence-Based RAG:** A cost-effective text-only alternative.

## 📊 Key Findings

- **Superior Accuracy:** The Smart MRAG system significantly outperformed text-only methods on questions requiring data from tables.
- **Reduced Hallucinations:** Providing visual context dramatically reduced the LLM's tendency to invent or misinterpret financial data.
- **Cost vs. Accuracy:** Multi-modal analysis has a higher token cost, but is justified for high-stakes financial analysis where accuracy is paramount.

For a full breakdown, see the [**Project Report**](./report/Smart%20MRAG%20for%20PDFs.pdf).

## 🛠️ Tech Stack

- **Core:** Python, LangChain, OpenAI API (GPT-4o)
- **Techniques:** Retrieval-Augmented Generation (RAG), Multi-Modality
- **Vector DB:** FAISS
- **Document Processing:** PyMuPDF (fitz), NLTK

## ⚙️ Setup

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/your-username/multimodal-rag-financial-analysis.git
    cd multimodal-rag-financial-analysis
    ```
2.  **Create a virtual environment and install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Set up your API Key:**
    Create a `.env` file and add your OpenAI key:
    ```
    OPENAI_API_KEY="your_sk_key_here"
    ```
4.  **Download Data:**
    Place the `Apple10k.pdf` file into the `data/` directory.

## 🚀 Usage

1.  Open `SmartRAG_final.ipynb` in a Jupyter environment.
2.  Ensure the file paths in the notebook are correct.
3.  Run the cells sequentially to see the analysis and results.
