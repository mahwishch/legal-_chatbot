Legal Research Chatbot
The Legal Research Chatbot is a powerful conversational AI tool that retrieves relevant legal documents and generates answers based on the Criminal Code of Canada and other legal texts. The chatbot utilizes a Retrieval-Augmented Generation (RAG) approach, leveraging a FAISS index for document retrieval and a T5 model for answer generation.

This repository contains the source code for building and deploying the chatbot, which can answer legal queries based on Canadian law.

Features
Document Retrieval: Uses FAISS to search for relevant legal documents based on the user’s query.
Answer Generation: Leverages a T5 model to generate responses based on the context of the retrieved documents.
Gradio Interface: A user-friendly interface where users can enter legal queries and receive AI-generated answers.
Deployment on Hugging Face Spaces: Easily deployable on Hugging Face Spaces for public use.
Install the required dependencies:

bash
Copy code
pip install -r requirements.txt
Download or create a FAISS index containing your legal documents. You can use the provided code in app.py to generate the FAISS index and save it locally. The FAISS index will be used for document retrieval.

Running the Chatbot Locally
Ensure the FAISS index is saved as faiss_index in the root directory.

Run the app.py script to start the Gradio interface:

bash
Copy code
python app.py
Visit the local interface at http://127.0.0.1:7860/ to interact with the chatbot.

Using Gradio Interface
Query Input: Enter your legal question (e.g., "What is the penalty for first-degree murder in Canada?").
Answer Output: The AI will retrieve relevant legal documents and generate a response based on the content of those documents.

Requirements
Here is the list of required libraries that should be included in requirements.txt:

txt
Copy code
pip>=22.3.1
gradio==3.0.0
transformers==4.12.0
tokenizers==0.10.3
langchain==0.0.108
faiss-cpu==1.7.2
torch==2.0.1
How It Works
Document Chunking:

Legal documents are split into chunks using the CharacterTextSplitter from LangChain to make it easier to search and process.
Embeddings:

The text chunks are embedded using Hugging Face Embeddings (sentence-transformers/all-mpnet-base-v2), transforming them into numerical vectors that can be compared using FAISS.
Document Retrieval:

FAISS is used to perform similarity search for the top 3 most relevant document chunks based on the user's query.
Answer Generation:

The relevant context from the documents is passed to a T5 model for answer generation. The model produces a natural language response based on the context provided.
License
This project is licensed under the MIT License - see the LICENSE file for details.

Contributing
Feel free to fork this repository, raise issues, or submit pull requests. Contributions are welcome to improve the functionality, enhance the user experience, or add new features.

Contact
For any questions, feel free to reach out to the project maintainer.

Email: mahwishch18@gmail.com


