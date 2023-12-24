# guide-bot
 A guide bot whose task is to search from Chapter 1 of Quran and Give meaningful answer 

 ![image](https://github.com/taaha3244/guide-bot/assets/120934618/b9d8237d-0077-4ba9-82b2-2ad509b9a1f2)


 Developing a Retrieval-Augmented Generation (RAG) application in LangChain
There are actually multiple ways to do RAG in LangChain.  In this small project, I will use the RetrievalQA chain. There are several steps in this process:


**Load documents**: LangChain provides multiple built-in document loaders, that work with PDF files, JSON files, or a Python file in your file directory.  We can use LangChain’s PyPDFLoader to import your PDF seamlessly.

**Split documents into chunks**: When our document is long, it’s necessary to split up our document text into chunks. There are various ways to split your text. Let’s just use the simplest method RecursiveTextSplitter to split based on characters and measure chunk length by the number of characters. 

**Create text embeddings**: The text chunks are then translated into numerical vectors through embeddings, allowing us to work with text data like semantic search in a computationally efficient manner. We can choose an embedding model provider like OpenAI for this task.

**Create a vector store**: We then need to store our embedding vectors in a vector store, which allows us to search and retrieve the relevant vectors at query time. 

**Create a retriever interface:** We can expose the vector store in a retriever interface. To retrieve text, we can choose a search type like “similarity” to use similarity search in the retriever object where it selects text chunk vectors that are most similar to the question vector.   

