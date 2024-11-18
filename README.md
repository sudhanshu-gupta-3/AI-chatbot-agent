Description:


The provided code builds a Streamlit-based chatbot application that allows users to interact with the content of a PDF file using a conversational AI model. It uses the LangChain framework for language model interaction, document processing, and memory management. The chatbot utilizes an FAISS vectorstore for efficient information retrieval and uses LLM embeddings to understand and answer user queries about the uploaded document.

Functionalities:


1. Upload and Process PDF Files
Users can upload a PDF file to the application using a file uploader.
The PDF content is loaded, split into smaller chunks for better processing, and indexed using FAISS.
2. Conversational AI Model
The application integrates ChatGroq with the LLAMA 3.1 model for answering questions.
The AI model uses the uploaded document's content to retrieve and generate context-aware responses.
3. Vectorstore for Document Search
A vectorstore is created from the document's chunks using HuggingFaceEmbeddings for semantic understanding.
This enables efficient retrieval of relevant sections from the document based on user queries.
4. Persistent Chat History
The application maintains a conversation history using st.session_state.
This ensures the chatbot remembers past interactions during a session for context continuity.
5. Memory Management
The application uses ConversationBufferMemory to store and retrieve conversational context during the interaction.
This allows for more natural and coherent multi-turn conversations.
6. Interactive Chat Interface
A user-friendly interface is provided where users can:
Upload their document.
Ask questions via a chat input.
View the AI's responses in a chat-like format.
Previous chat history is displayed in the interface.


Workflow of the Application:

Document Upload:

Users upload a PDF file via the file uploader.
The file is stored locally, and its content is processed into manageable chunks.

Document Processing:

The text is split using the CharacterTextSplitter.
The chunks are embedded and indexed using FAISS, enabling quick semantic search.

Chain Initialization:

A conversational retrieval chain is set up using:
The LLM (LLAMA 3.1).
The retriever (based on the vectorstore).
The conversation memory.

Chat Interaction:

Users enter questions via the chat input.
The system retrieves relevant content from the document and generates responses using the LLM.
Conversation Management:

The assistant's response and user's input are appended to the session's chat history.
The chat history ensures that the system maintains context across multiple user queries.

Key Components:

Streamlit Frontend:

Provides the UI for user interaction, including file upload and chat interface.
LangChain Components:

UnstructuredPDFLoader: To load and read PDF content.
CharacterTextSplitter: To split large documents into smaller, manageable chunks.
FAISS: A vectorstore for efficient retrieval of document chunks.
HuggingFaceEmbeddings: For generating vector embeddings from the document content.
ChatGroq: The LLM used for generating responses.
ConversationBufferMemory: Manages chat context and history.
Conversational Retrieval Chain: Combines the LLM, retriever, and memory for seamless question answering.
