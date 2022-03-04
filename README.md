# NLP-Project_Automatic-Question-Answering-from-FQAs
Automatic Question Answering from FQAs using Word Embeddings


In this project, we examine the task of automatically retrieving a suitable response to user questions from FAQs. Often websites have comprehensive FAQs, but manually searching and finding the answer to a specific question from these FAQs is not trivial. The purpose of this exercise is to answer user queries by automatically retrieving the closest question and answer from predefined FAQs when appropriate.

We will use a sample dataset of FAQs extracted from the site https://www.fda.gov/emergency-preparedness-and-response/coronavirus-disease-2019-covid-19/covid-19-frequently-asked-questions for this task. This dataset can be replaced with a more elaborate dataset as appropriate.

Our basic strategy is as follows: For a given query, find the FAQ question that is closest in meaning to the user query and display it to the user. For this, we need to have an efficient way of computing Semantic Similarity between two sentences.

To compute Semantic Similarity between sentences, we will convert each sentence into a vector. We can then use cosine similarity between vectors to come up with a distance measure between sentences that indicates how similar they are in meaning.

Reference: https://youtu.be/ZxR38An5TQE

### Methodology 
Answer user queries by automatically retrieving the closest question and answer from predefined FAQs.

![image](https://user-images.githubusercontent.com/93287801/156742587-8f4ef7de-750a-47b3-b68b-f20b85fd5f9b.png)


Compute Semantic Similarity between sentences.

Convert each sentence into a vector - Bag of Words, Word2Vec - Skipgram, Glove, BERT

![image](https://user-images.githubusercontent.com/93287801/156742671-0adc9af9-e5d6-4a93-bf7d-f4e66f833a46.png)

![image](https://user-images.githubusercontent.com/93287801/156742711-9d98d08f-695a-4302-956a-4ae71eee3df2.png)

### Word2Vec Embeddings

Word2Vec embeddings are popularly trained using the skipgram model. These embeddings are trained to take a word as input and reconstruct its context. As a result, they are able to take into account semantic similarity of words based on context information. The resulting embeddings are such that words with similar meaning tend to be closer in terms of cosine similarity.

### Skipgram model

The most popular word2vec model is the skipgram model. Particularly, the most commonly used pre-trained model is based on the Google News dataset that has 3 billion running words and creates upto 300 dimensional embedding for 3 Million words
You can find more information on the following page : https://code.google.com/archive/p/word2vec/

The relationship between words is derived by cosine distance between words. Such word vectors are good at answering analogy questions.
Semantically similar words are close together.
We can also use arithmetic on these embeddings to derive meaning.

![image](https://user-images.githubusercontent.com/93287801/156742824-9441331c-fdae-4032-b520-caa35bc9cd70.png)

Word2Vec is a feed forward neural network based model to find word embeddings. There are two models that are commonly used to train these embeddings: The skip-gram and the CBOW model.
The Skip-gram model takes the input as each word in the corpus, sends them to a hidden layer (embedding layer) and from there it predicts the context words. Once trained, the embedding for a particular word is obtained by feeding the word as input and taking the hidden layer value as the final embedding vector.
The CBOW (Continuous Bag of Words) model takes the input the context words for the given word, sends them to a hidden layer (embedding layer) and from there it predicts the original word. Once again, after training, the embedding for a particular word is obtained by feeding the word as input and taking the hidden layer value as the final embedding vector.

![image](https://user-images.githubusercontent.com/93287801/156742936-f39f5e31-6255-4c5a-96bd-a4098bfe9466.png)


BERT EMBEDDINGS

Bidirectional Encoder Representations from Transformers

https://www.blog.google/products/search/search-language-understanding-bert/

Instead of looking at words in isolation, BERT, a transformer based model attempts to use the context of words to get embeddings. BERT broke several records in NLP tasks in 2018, a huge leap in NLP. BERT uses several concepts in deep learning to come up with a model that looks at context in a bi-directional fashion, leveraging information from the entire sentence as a whole through self-attention.

Take a look at https://www.analyticsvidhya.com/blog/2019/09/demystifying-bert-groundbreaking-nlp-framework/ for more information on BERT.

Google included examples demonstrating the effects of BERT in its announcement. One of the examples compared search results before and after the update for the query: “2019 brazil traveler to usa need a visa.”

The intent of the search query is to find results related to visa information for Brazilian travelers coming to the U.S. Initially, the search engine misinterprets the meaning of the word “to,” causing the search engine to display results on U.S. citizen travel to Brazil. After the update, the engine understands the true intent of the search and appropriately displays information on U.S. travel visas.

![image](https://user-images.githubusercontent.com/93287801/156743008-39087253-e639-4538-bff0-2b4217b11447.png)


Use cosine similarity between vectors to come up with a distance measure between sentences that indicates how similar they are in meaning

