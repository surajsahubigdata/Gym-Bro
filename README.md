# Gym-Bro Diet Assistant
## Project Overview
Gym-Bro Diet Assistant is a Streamlit-based chatbot application designed to help users find diet plans or nutritional advice by extracting information from a collection of documents (like PDFs). The chatbot uses LangChain's LLM and retrieval chains to answer diet-related queries based on the content of these documents. The project integrates FAISS for document vectorization and Hugging Face embeddings for natural language processing, enabling fast, context-aware responses.

## Key Features:
+ **Streamlit Interface**: A simple and interactive web-based UI for entering questions about diet.
+ **Document Ingestion and Embedding**: The app loads and splits documents, converts them into vector embeddings using Hugging Face models, and stores them in a FAISS vector store for quick retrieval.
+ **LLM Integration**: It uses Groq API to leverage the Llama3-8b-8192 model for generating responses based on retrieved documents.
+ **Retrieval-Based QA**: Questions are answered by retrieving relevant document sections and passing them to the LLM, ensuring answers are grounded in provided materials.
+ **PDF Directory Loader**: Easily ingests PDFs from a folder, making the app flexible for various types of documents.

## Tech Stack:
+ **Streamlit**: For front-end UI and user interaction.
+ **LangChain**: For chain creation, including document retrieval and language model invocation.
+ **Groq API**: For leveraging Llama-based large language models.
+ **FAISS**: For vector storage and efficient similarity searches.
+ **Hugging Face Embeddings**: For converting documents into vectors.
+ **PyPDFDirectoryLoader**: For loading and reading PDF documents from a specified directory.
+ **dotenv**: To manage API keys and sensitive data securely.

## How It Works:
+ **Document Embedding**: On clicking the "Document Embedding" button, the app loads PDF files from the specified directory, splits the text, and creates vector embeddings for efficient document retrieval.
+ **Ask a Question**: Users input a question in the text box (e.g., "Tell me what kind of diet I need today").
+ **Response Generation**: The app retrieves relevant documents using FAISS and passes them to the Groq LLM via LangChain. The LLM generates an answer based on the provided document context.
+ **Document Similarity Search**: The app displays the most relevant document sections, showing the user how the response was derived.

## Installation & Setup:
### Prerequisites:
+ Python 3.8 or above
+ Streamlit
+ LangChain
+ FAISS
+ Hugging Face Transformers
+ Groq API Key
+ dotenv

### Instructions:
+ Clone the Repository:

    Inline `code`

    git clone https://github.com/surajsahubigdata/Gym-Bro.git

+ Create virtual environment and install the required packages:

    Inline `code`

    conda create -p venv python==3.10

    pip install -r requirements.txt

+ Create a .env file in the project root directory and add your API keys:

    Inline `code`

    GROQ_API_KEY=your_groq_api_key
    HF_TOKEN=your_hugging_face_token

+ Run the app:

    Inline `code` streamlit run app.py

## Usage:
+ To start using the app, load your documents (PDFs) into the Encyclopedia directory.
+ Start the app, embed the documents using the "Document Embedding" button.
+ Ask questions via the input field and receive context-aware responses based on the embedded documents.

