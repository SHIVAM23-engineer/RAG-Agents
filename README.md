
## README: RAG-Based Agent for Document Retrieval and Question Answering


Overview
This project demonstrates the implementation of a RAG-based (Retrieval-Augmented Generation) agent that answers user queries by retrieving information from provided documents. The agent does not use external tools or sources, and all answers are strictly derived from the embedded documents, ensuring a zero-cost setup in terms of additional API costs for external information retrieval.

The RAG system utilizes LangChain to manage document processing, question reformulation, and retrieval. The core language model used for embedding and generating responses is Ollama Gemma, and document storage is handled using the FAISS vector database for fast and efficient retrieval.

Features
Cost-Free Setup: The agent strictly uses embedded documents and does not rely on external APIs for querying the web or other databases, making it zero-cost for retrieval.
Document-Based Question Answering: The agent answers questions using only the provided documents, adhering to the following rules:
If no relevant information is found in the documents, it responds with "I don't know".
When information is present, it compares details from multiple documents if applicable, before providing a concise answer.
History-Aware Retrieval: The agent is capable of reformulating questions based on conversation history, allowing for better context-aware responses.
Documents Used
American Football.pdf: Information related to American football.
British Football.pdf: Information related to British football.
Key Components
Document Loading & Splitting:

PDFs are loaded and split into chunks using PyPDFLoader and CharacterTextSplitter for efficient embedding.
Embedding & Retrieval:

Document chunks are embedded using the Ollama Gemma model, and stored in a FAISS vector database for fast retrieval.
A history-aware retriever reformulates questions using conversation history for better context understanding.
Agent Behavior:

The agent is created using the React framework from LangChain, which processes documents using retrieval tools.
Answers are formulated solely based on the documents, ensuring accuracy and cost-free operations.
Prompt Templates:

Contextualization Prompt: Reformulates questions based on chat history.
Question Answering Prompt: Directs the agent to answer based only on the provided documents.
Example Usage
The agent can be tested with various queries like:

"Explain British football."
"Compare British football and American football."
"What is the capital of France?" (The agent will respond with "I don't know" if the answer is not in the documents).
