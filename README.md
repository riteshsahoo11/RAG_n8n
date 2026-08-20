🚀**Overview**

    This project implements a fully automated Retrieval-Augmented Generation (RAG) chatbot using n8n. 
    It is split into two seamless workflows: an automated data processing pipeline that ingests documents 
    directly from Google Drive, and a conversational AI agent powered by Google Gemini that retrieves 
    and answers questions based on that data.

🛠️ **Architecture Diagram**
        
[n8n diagram code.txt](https://github.com/user-attachments/files/31255254/n8n.diagram.code.txt)
graph TD
    subgraph Phase 1: Data Processing
        A[Google Drive Trigger] -->|File Created| B(Download File)
        B --> C{Text Splitter}
        C -->|Chunk Size: 500| D[OpenAI Embeddings]
        D --> E[(Pinecone Vector Store)]
    end

    subgraph Phase 2: Retrieval Agent
        F[n8n Chat Trigger] --> G{AI Agent}
        H[Google Gemini LLM] --> G
        I[Simple Memory] --> G
        J[OpenAI Embeddings] --> K[(Pinecone Tool)]
        K -.->|Retrieves Context| G
    end
