Here's a complete step-by-step guide to get Ollama running with the uncensored dolphin-mistral:7b model on your PC.

Step 1: Install Ollama
First, you need to install the Ollama application. Open your terminal or command prompt and run the following command.

For Linux or macOS:

bash
> curl -fsSL https://ollama.ai/install.sh | sh
This script automatically detects your operating system and installs Ollama in the correct location.

For Windows:

Download the installer from: https://ollama.ai/download/OllamaSetup.exe
Double-click the downloaded .exe file.
Follow the installation wizard prompts.
After installation, you must close and restart your terminal (or open a new one) for the ollama command to be recognized.
Step 2: Verify the Installation
After installation, verify that Ollama is running correctly.

For Linux/macOS:

bash
# Check if the Ollama service is active
> sudo systemctl status ollama
If it's not active, start it with:

bash
> sudo systemctl start ollama
For Windows:
The Ollama service should start automatically. You can check by opening Task Manager and looking for ollama.exe.

Now, test the command line tool:

bash
> ollama --version
This should print the installed version of Ollama.

Step 3: Download the Dolphin-Mistral Model
This is the step where you download the uncensored AI model. The model is about 4.1 GB, so it may take a few minutes depending on your internet speed.

bash
> ollama pull dolphin-mistral:7b
You will see a progress bar in your terminal as the model downloads.

Step 4: Start Chatting with the Model
Once the download is complete, you can start an interactive chat session directly in your terminal.

bash
> ollama run dolphin-mistral:7b
Your terminal prompt will change to >>>. You can now type your questions. For example:

>>> What are the main phases of a penetration test?
To exit the chat session, type /bye and press Enter.

Step 5: (Optional but Recommended) Install a Web Interface
Typing in a terminal can be limiting. A web interface gives you a much better ChatGPT-like experience. Open WebUI is a popular and easy-to-use option.

Install Python and Pip: If you don't have them, install Python 3.8+ and pip from the official website (python.org).

Install Open WebUI: Open a new terminal window and run:

bash
> pip install open-webui
Start the Web Interface:

bash
open-webui serve --port 8080
This command starts the web server. Keep this terminal window open while you use the interface.

Access the Interface: Open your web browser and go to:
http://localhost:8080

First-Time Setup:

The first time you visit, you'll be asked to create an account (this is local to your machine).
After signing in, click the "Select a model" dropdown at the top.
You should see dolphin-mistral:7b in the list. Select it.
You can now start chatting with the uncensored model through the friendly web interface.
Step 6: (Optional) Integrate Your Cybersecurity Books
To make the AI use your book collection, you'll set up a RAG (Retrieval-Augmented Generation) system. This is more advanced but directly addresses your goal.

Install RAG Libraries: In the same terminal where you installed Open WebUI (or a new one), install the necessary libraries:

bash
pip install chromadb sentence-transformers pypdf2
Create a Python Script to Process Your Books:
Create a new file named process_books.py and paste the following code into it.

python
import os
from pypdf2 import PdfReader
from sentence_transformers import SentenceTransformer
import chromadb
import textwrap

# --- Configuration ---
PDF_DIRECTORY = "/path/to/your/cybersecurity/books"  # <-- IMPORTANT: CHANGE THIS PATH
CHROMA_DB_PATH = "./cybersecurity_db"
CHUNK_SIZE = 1000  # Number of characters per chunk
CHUNK_OVERLAP = 200 # Overlap between chunks to maintain context

# --- 1. Extract Text from PDFs ---
def extract_text_from_pdfs(pdf_dir):
    print(f"Searching for PDFs in: {pdf_dir}")
    documents = []
    for filename in os.listdir(pdf_dir):
        if filename.endswith(".pdf"):
            filepath = os.path.join(pdf_dir, filename)
            print(f"Processing: {filename}")
            try:
                reader = PdfReader(filepath)
                text = ""
                for page in reader.pages:
                    page_text = page.extract_text()
                    if page_text:
                        text += page_text + "\n"
                if text.strip():
                    documents.append({"text": text, "source": filename})
            except Exception as e:
                print(f"Could not read {filename}: {e}")
    print(f"Successfully extracted text from {len(documents)} books.")
    return documents

# --- 2. Chunk Text ---
def chunk_documents(documents, chunk_size, chunk_overlap):
    print("Chunking documents...")
    chunks = []
    for doc in documents:
        # Simple text wrapping for chunking
        text_chunks = textwrap.wrap(doc['text'], width=chunk_size, replace_whitespace=False, drop_whitespace=False)
        for i, chunk in enumerate(text_chunks):
            chunks.append({
                "text": chunk,
                "source": doc['source'],
                "chunk_id": i
            })
    print(f"Created {len(chunks)} chunks.")
    return chunks

# --- 3. Create Embeddings and Store in ChromaDB ---
def create_vector_db(chunks, db_path):
    print("Creating vector database...")
    # Use a lightweight embedding model
    embedding_model = SentenceTransformer('all-MiniLM-L6-v2')
    
    client = chromadb.PersistentClient(path=db_path)
    
    # Clear existing collection if it exists
    try:
        client.delete_collection("cybersecurity_books")
    except:
        pass
        
    collection = client.get_or_create_collection("cybersecurity_books")

    batch_size = 100
    for i in range(0, len(chunks), batch_size):
        batch = chunks[i:i+batch_size]
        texts = [c['text'] for c in batch]
        metadatas = [{'source': c['source'], 'chunk_id': c['chunk_id']} for c in batch]
        ids = [f"{c['source'].replace('.pdf', '')}_{c['chunk_id']}" for c in batch]

        embeddings = embedding_model.encode(texts).tolist()
        
        collection.add(
            documents=texts,
            metadatas=metadatas,
            ids=ids,
            embeddings=embeddings
        )
        print(f"Processed batch {i//batch_size + 1}/{(len(chunks) + batch_size - 1)//batch_size}")
    
    print(f"Vector database created at {db_path}")
    return collection

# --- Main Execution ---
if __name__ == "__main__":
    # IMPORTANT: Edit this line to the folder where your PDF books are stored.
    # Example for Windows: "C:\\Users\\YourUser\\Documents\\CyberSecBooks"
    # Example for Linux/Mac: "/home/youruser/docs/cybersec_books"
    pdf_directory = PDF_DIRECTORY 
    if pdf_directory == "/path/to/your/cybersecurity/books":
        print("!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!")
        print("!!! PLEASE EDIT THE 'PDF_DIRECTORY' variable in the !!!")
        print("!!! script to point to your books folder.         !!!")
        print("!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!!")
        exit()

    docs = extract_text_from_pdfs(pdf_directory)
    if not docs:
        print("No documents were processed. Exiting.")
        exit()

    text_chunks = chunk_documents(docs, CHUNK_SIZE, CHUNK_OVERLAP)
    db_collection = create_vector_db(text_chunks, CHROMA_DB_PATH)
    print("\nSetup complete! Your books are now ready to be used.")
Run the Script:

Crucially, edit the PDF_DIRECTORY variable in the script to point to the actual folder where your cybersecurity PDFs are saved.
Save the file and run it from your terminal:
bash
python process_books.py
This will take some time, depending on how many books you have. It's reading them, breaking them into chunks, and creating a searchable database.

Step 7: Use Your Knowledge Base with the AI
Now you need a way to query your new database and feed the results to the AI. Create another file named query_ai.py.

python
from sentence_transformers import SentenceTransformer
import chromadb
import ollama

# --- Configuration ---
CHROMA_DB_PATH = "./cybersecurity_db"
MODEL_NAME = "dolphin-mistral:7b"
