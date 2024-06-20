# Chat with Multiple PDFs

## Project Overview

This project is a Streamlit application that allows users to upload multiple PDF documents and interact with them using natural language questions. The application uses natural language processing (NLP) techniques to extract text from PDFs, create embeddings for document retrieval, and generate responses using a pre-trained T5 model. The system leverages FAISS for efficient similarity search and Sentence-BERT for embedding generation.

## Installation Instructions

Follow these steps to set up the environment and run the project:

1. **Clone the repository:**
    ```bash
    git clone https://github.com/mkshitij1763/Chat-with-PDF.git
    cd Chat-with-PDF
    ```

2. **Set up a virtual environment (optional but recommended):**
    ```bash
    python3 -m venv venv
    source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
    ```

3. **Install the required libraries:**
    ```bash
    pip install -r requirements.txt
    ```

4. **Download the T5 model:**
    Run the following script to download and save the T5 model locally.
    ```python
    from transformers import AutoTokenizer, AutoModelForSeq2SeqLM

    tokenizer = AutoTokenizer.from_pretrained("MBZUAI/LaMini-T5-738M")
    model = AutoModelForSeq2SeqLM.from_pretrained("MBZUAI/LaMini-T5-738M")

    tokenizer.save_pretrained("MBZUAI/LaMini-T5-738M")
    model.save_pretrained("MBZUAI/LaMini-T5-738M")
    ```

5. **Run the Streamlit application:**
    ```bash
    streamlit run app.py
    ```

## Usage

1. **Upload PDF Documents:**
   - In the sidebar, upload one or more PDF files by clicking on the "Upload your PDFs here and click on 'Process'" button.
   - Click the "Process" button to extract and process text from the uploaded PDFs.

2. **Ask Questions:**
   - Once the PDFs are processed, type your question in the text input box at the top of the page.
   - Press Enter to submit your question.
   - The system will retrieve relevant text from the documents and generate a response, which will be displayed in the chat interface.

### Example

1. **Upload PDFs:**
   - Upload a PDF document containing information about a specific topic (e.g., a research paper).

2. **Ask a Question:**
   - Type a question such as "What are the main findings of the study?"
   - The system retrieves relevant sections from the document and generates a response summarizing the main findings.

## Dependencies

- `streamlit`: Web application framework for creating the interactive UI.
- `PyPDF2`: Library for reading PDF files.
- `langchain`: Utility for splitting text into manageable chunks.
- `sentence-transformers`: Library for creating embeddings using Sentence-BERT.
- `faiss`: Library for efficient similarity search.
- `transformers`: Library for loading and using pre-trained NLP models.

### requirements.txt
```text
streamlit==1.6.0
PyPDF2==2.12.1
langchain==0.4.0
sentence-transformers==2.2.2
faiss-cpu==1.7.2
transformers==4.19.2
numpy==1.21.4
```

Ensure you have the correct versions of the libraries by installing them using the provided `requirements.txt` file.

## Contact

For any questions or issues, please contact [mkshitij1763@gmail.com].

---
