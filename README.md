# Project Description
This project builds a simple yet effective Retrieval-Augmented Generation (RAG) system that allows users to ask questions about any topic using real-time Wikipedia content. It combines document retrieval techniques with powerful transformer models to provide accurate answers. The system fetches relevant Wikipedia articles, breaks them into manageable chunks, indexes them using FAISS, and retrieves the most relevant parts based on user queries. A pretrained question-answering model is then used to generate precise answers, demonstrating a practical use of NLP and LLM.

## Step-by-Step Breakdown:
### Step 1 : Install Required Libraries
The code begins by installing wikipedia, faiss-cpu, transformers, and sentence-transformers, which are essential for fetching content, generating embeddings, indexing, and performing question answering.

### Step 2 : Import Required Classes
Necessary libraries are imported from Hugging Face’s transformers, sentence-transformers, and wikipedia modules. These include tokenizers, models, pipelines, and the FAISS indexing library.

### Step 3 : Retrieve Wikipedia Content
The user is prompted to enter a topic. The wikipedia library fetches the content of the corresponding article. If the topic is ambiguous or invalid, the code handles the exception and prompts the user accordingly.

### Step 4 : Split Wikipedia Content into Chunks
The Wikipedia text is split into smaller overlapping chunks using a tokenizer from the sentence-transformers/all-mpnet-base-v2 model. This step ensures that the information fits within model limits and preserves context between segments.

### Step 5 : Generate Embeddings and Create FAISS Index
Each chunk is converted into a vector (embedding) using a pretrained sentence transformer. These vectors are then added to a FAISS index, enabling efficient similarity search to retrieve relevant text later.

### Step 6 : Query the Index with a Question
The user enters a question related to the topic. The question is also converted into an embedding and compared against the indexed chunks. The top 3 most similar chunks are retrieved and printed for review.

### Step 7 : Answer the Question Using a QA Model
A question-answering pipeline is created using the deepset/roberta-base-squad2 model. The retrieved chunks are passed as context, and the model generates a direct answer to the user's question.

# Summary:
This project uses Wikipedia articles and transformer-based models to answer user questions. It combines document retrieval (FAISS and sentence embeddings) with language understanding (QA pipeline) to simulate a basic RAG system. The flow involves fetching data, chunking text, indexing embeddings, retrieving relevant content, and generating answers. This demonstrates how transformer models can be used for intelligent question answering over large text corpora.

