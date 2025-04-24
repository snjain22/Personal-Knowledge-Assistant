# Personal Knowledge Assistant

A Python-based RAG (Retrieval Augmented Generation) system that allows you to query your personal documents using natural language. This assistant indexes your documents in a vector database and uses large language models to provide accurate answers based on your personal knowledge base.

## Features

- **Document Processing**: Support for various document formats (PDF, TXT, DOCX, Markdown)
- **Vector Search**: Efficient similarity search using FAISS
- **RAG Implementation**: Combines retrieval with generative AI for accurate responses
- **Source Attribution**: Cites the sources used to generate answers
- **Multiple Interfaces**: Command-line and web interface (Streamlit)
- **Flexible LLM Support**: Works with OpenAI models or local models via Ollama

## Requirements

- Python 3.8+
- OpenAI API key (optional, if using OpenAI models)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/snjain22/Personal-Knowledge-Assistant.git
cd Personal-Knowledge-Assistant
```

2. Install required packages:
```bash
pip install langchain faiss-cpu python-dotenv openai sentence-transformers unstructured streamlit
```

3. Set up your environment variables (optional if using environment variables):
```bash
# For OpenAI API
export OPENAI_API_KEY=your_api_key_here
```

## Project Structure

```
personal-knowledge-assistant/
├── app.py                  # Main CLI application
├── streamlit_app.py        # Web interface using Streamlit
├── document_processor.py   # Document ingestion and chunking
├── embedding_indexer.py    # Vector embeddings and FAISS integration
├── rag_chain.py            # Retrieval and generation pipeline
├── chatbot.py              # Assistant interface
├── documents/              # Directory to store your documents
├── knowledge_base/         # Directory for the FAISS index
└── temp_uploads/           # Temporary storage for uploaded files (web interface)
```

## Usage

### Command Line Interface

1. Place your documents in the `documents` directory
2. Run the CLI application:
```bash
python app.py
```
3. Enter your queries when prompted

### Web Interface

1. Start the Streamlit app:
```bash
streamlit run streamlit_app.py
```
2. Open your browser and go to `http://localhost:8501`
3. Upload your documents through the interface
4. Click "Process Documents and Initialize"
5. Start asking questions about your documents

## Configuration Options

- **LLM Selection**: Choose between OpenAI models or local models (via Ollama)
- **Vector Store**: Customize embedding model and vector search parameters
- **Document Processing**: Adjust chunk size and overlap for better retrieval
