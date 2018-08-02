# Topic_Modelling_and_Summarization

## Approach:

### Task 1 

#### Finding the topics in the given Dataset :

I have implemented two different topic modelling techniques as follows:

1. Latent Dirichlet Allocation (LDA)

2. Non-negative Matrix Factorization (NMF)

I have vectorized the raw text with CountVectorizer, the dual stages of tokenizing and stopwords filtering are automatically included as a high-level component.
Sklearn's tokenizer discards all single character terms like ('a', 'w' etc) and also lower cases all terms by default. Filtering out stopwords in Sklearn is as convenient as passing the value 'English' into the argument "stop_words" where a built-in English stopword list is automatically used.
Here I have essentially inherited and subclassed the original Sklearn's CountVectorizer class and overwritten the build_analyzer method by implementing the lemmatizer for each list in the raw text matrix.
In LDA and NMF, the modelling process revolves around three things: the text corpus, its collection of documents, D and the words W in the documents.
I have 1st implemented LDA for topic modelling and plotted the top 40 words in a wordcloud. But the results didn't seem to be quite accurate.
Then I tried the same process with NMF for topic modelling and plotted the top 40 words in a wordcloud, it was very accurate as it completely segregated the words of the 2 topics clearly without any ambiguity.
So, I have used NMF for further processes. 


### Task 2 

#### Clustering all the documents related to each of the topics:

I sorted all the documents in each topic on the basis of NMF Document score separately. And then applied Postprocessing Logic based on NMF Document Score.
In the postprocessing logic, I removed those documents which are of less importance to the topic compared to the other topic based on the NMF Document Score.


### Task 3 

#### Topic Summarization:

For Summarization, I have just taken the list of the top 3 articles in each topic as the summary of the whole topic. I know it seems like a very simple approach but it gives a very human-readable summary of all the salient features


