🚀**Overview**

    This project implements a fully automated Retrieval-Augmented Generation (RAG) chatbot using n8n. 
    It is split into two seamless workflows: an automated data processing pipeline that ingests documents 
    directly from Google Drive, and a conversational AI agent powered by Google Gemini that retrieves 
    and answers questions based on that data.

🛠️ **Architecture Diagram**



 ✨ **Key Features**

    🔼 Automated Data Ingestion: Automatically triggers the workflow whenever a new file is uploaded to a specific Google Drive folder.
    🔼 Smart Document Chunking: Processes documents using a Recursive Character Text Splitter with a configured chunk size of 500 and an overlap of 200.
    🔼 Advanced Vector Storage: Generates vector embeddings via OpenAI and stores them securely in a Pinecone index named
    🔼 Intelligent Conversational Agent: Utilizes the Google Gemini Chat Model to interpret user queries and generate accurate, context-aware responses.  
    🔼 Contextual Awareness: Integrates a Memory Buffer Window to remember conversation history and maintain context during chat sessions.

⚙️ **Setup Instructions**

    - Import Workflows: Download the provided JSON files and import them directly into your n8n workspace.
    - Configure Credentials: Set up and authenticate your API nodes for Google Drive, OpenAI, Pinecone, and Google Gemini (PaLM).
    - Target Folder: Update the Google Drive Trigger node with the specific folder ID you wish to monitor for new uploads.
    - Activate & Chat: Toggle both workflows to "Active," upload a test document to Drive, and use the n8n Chat Trigger interface to start interacting with your data.
