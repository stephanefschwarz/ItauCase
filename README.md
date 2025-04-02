# TO DO

### Preprocessing

Default preprocessing from the user input string respective:

- [ ] Set all text sentence to lower
- [ ] Remove special characters and punctuation
- [ ] Remove extra write space in the beging and end of the sentence
- [ ] Remove word accents

> [!NOTE]
> Below I list a set of preprocessing we can evaluate during inference time, however, I don't believe it will improve the matching processing once it can increase the edit distance (increase the discimilarity) between the original company name and the one provided by the end user, specially in case the user passed the correct name.

- [ ] Deduplicate repeated words
- [ ] Stemming
- [ ] Lemmatization
- [ ] Remove Stop Words

### Searching strategies

#### Distance Metrics
- [ ]  Cosine
- [ ]  Euclidean
- [ ]  Manhattan
- [ ]  Minkowski
- [ ]  SEuclidean
- [ ]  Mahalanobis
- [ ]  Hamming
- [ ]  Canberra
- [ ]  BrayCurtis

#### Embeddings
- [ ] Bag-of-words normalized with TF-IDF
- [ ] Multilingual Dense Embeddings
- [ ] Hashing Vectorizer

#### Techniques
- [ ] Clustering (Leiden, RAC)
- [ ] Knowledge Graph
- [ ] Ranking
- [ ] Edit Distance
- [ ] Contrastive Learning
- [ ] Fuzzy Matching
- [ ] Semantic Search

## Challanges

One of the biggest challanges of this case is to search on two list quickly. We have the razão social and the nome fantasia fields to compare with the input provided by the user. 

We cannot combine both one it can cause an extra effort for the model find the correct match, and by search into both sequentially, will cause an significan increase in the inference time reponse considering in a real world enviroument we will have millions of names to search for. 




