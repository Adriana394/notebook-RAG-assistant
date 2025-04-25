# Notebook RAG Assistant

A **Retrieval-Augmented Generation (RAG)** assistant that indexes and queries your personal Colab notebooks.

## Features

- Loads `.ipynb` files from a local directory or Google Drive.
- Splits notebook content into semantic chunks.
- Generates vector embeddings using OpenAI and stores them in a Chroma database.
- Supports conversational queries with memory (multi-turn dialogue).
- Returns not only answers but also the **names of the notebooks** containing the relevant content.
- Easy deployment via Gradio.

## Prerequisites

- Python 3.8+  
- An OpenAI API key  
- (Optional) Google Drive mount in Colab or local sync via Google Drive for Desktop

## Installation

1. Clone this repo:
   ```bash
   git clone https://github.com/your-username/notebook-rag-assistant.git
   cd notebook-rag-assistant
   ```

2. Set up a virtual environment:
   ```bash
   python -m venv .venv
   source .venv/bin/activate      # Linux/macOS
   .venv\Scripts\activate         # Windows
   ```
3. Install dependencies 
   ```bash
   pip install -r requirements.txt
   ```

## Environment Variables

Create a file named .env in the project root with the following entries:

   ```
   NOTEBOOKS_DIR=/path/to/your/notebooks

   VECTOR_DB_DIR=/path/to/chroma_db

   OPENAI_API_KEY=sk-...
   ```
- **NOTEBOOKS_DIR**: Directory containing your .ipynb files.
- **VECTOR_DB_DIR**: Directory where Chroma persists the embeddings.
- **MODEL_API_KEY**: Your MODEL API key.

## Usage
1. **Open the Notebook**

   Launch Notebook-RAG-Assistant.ipynb in Jupyter Lab or Google Colab.
2. **Run All Cells**

   Execute each cell in order. The final cell will start a Gradio chat interface.
3. **Ask Questions**

   In the Gradio interface, ask queries such as:
   ```
   Which notebooks contain the statement `import torch`?
   ```

