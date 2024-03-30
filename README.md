# Chat with your data

This repository is based on the deeplearning.ai course [Chat with your data](https://www.deeplearning.ai/short-courses/langchain-chat-with-your-data/)

The purpose of the course is to show you how you can build applications using LangChain, OpenAI embeddings, vector store such as Chroma DB to be able to "chat" with your own data.

----
# Lessons 

## Lesson 1 - Document loading

Your data is usually structured or unstructured, and to be able to talk with it, you need to load it, so that, you can start working on it, such as: 

- Exploring what is the content of your data
- Splitting it into smaller chunks of data so it can be readable by models 
- Pre-processing it before it's transformed into an embedding 

On this lesson, the facilitator gives you an intuition of the different loaders available, such as PDF, WebLoaders and Video loaders like Youtube. 

Note: I ran into an issue using the Youtube loader, perhaps because now youtube blocks this kind of content. If you find a solution feel free to open an issue with the solution.

## Lesson 2 - Document splitting 

Usually, once we have loaded our data and have it ready to be used, we need to do a bit more steps, such as transform it into smaller chunks, so it can fit the model context window, or perhaps you wish to do certain transformations before passing it to the model like filtering. 

Those are the differen [text splitters](https://python.langchain.com/docs/modules/data_connection/document_transformers/#types-of-text-splitters) supported by LangChain

On this lesson, the facilitator walks us through 2 main splitters: 

1. Recursive splitter, which as its name says, splits recursively the text. 
2. Character splitter, which use a set of defined characters. 

There is also a way to build context character splitters, in this case is done using the Markdown text splitter, where you define the sections and the split will be done according to the sections provided to split on. 

## Lesson 3 - Vector stores and embeddings 

Nice, nearly there! Once we have our data already split into smaller chunks, we need to be able to transform the "text" of this data into a readable format for the model, and for doing so, we can use [OpenAI Embedding](https://platform.openai.com/docs/guides/embeddings) models. 

Basically, an Embedding model, takes text and transform it into multi-dimensional vectors in the space that can help you to identify for example, what phrases, words are similar to each other. 

On this lesson, the facilitator goes through an small example using sentences to be able to compare them between each other, to later on, take Lecture notes from CS229 and pass it through embeddings and store those into a vector store such as [Chroma DB](https://www.trychroma.com)

Well, after you have all your vectors indexed into a vector store you can start asking questions, such as: 

- What is the most basic algorithm in Machine learning? 

and the vector store will retrieve the top N vectors that are most similar to the question being asked.