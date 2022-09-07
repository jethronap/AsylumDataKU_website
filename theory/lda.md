# Latent Dirichlet Allocation (LDA)


Latent Dirichlet Analysis (LDA) is a probabilistic, generative model which uncovers the topics latent to a dataset by assigning weights to words in a corpus, where each topic will assign different probability weights to each word.

For a given corpus, a topic model estimates a topic distribution for each of its documents (i.e., a distribution of weights over a set of topics), where a topic is itself a distribution of weights over the vocabulary of the corpus. The most weighted words of each topic are syntactically and/or semantically related, given that collection of documents. This means that two distinct topics can share the exact same vocabulary, but have different weight distributions.

The LDA algorithm first models documents via a mixture model of topics. From these topics, words are then assigned weights based on the probability distribution of these topics. It is this probabilistic assignment over words that allow a user of LDA to say how likely a particular word falls into a topic. Subsequently, from the collection of words assigned to a particular topic, are we thus able to gain an insight as to what that topic may actually represent from a lexical point of view.


## Assumptions

- Each document is just a collection of words or a “bag of words”. Thus, the order of the words and the grammatical role of the words (subject, object, verbs, …) are not considered in the model.
- Words like am/is/are/of/a/the/but/… don’t carry any information about the *topics* and therefore can be eliminated from the documents as a preprocessing step. In fact, we can eliminate words that occur in at least %80 ~ %90 of the documents, without losing any information. For example, if our corpus contains only medical documents, words like human, body, health, etc. might be present in most of the documents and hence can be removed as they don’t add any specific information which would make the document stand out.
- We know beforehand how many topics we want. Meanining the number of topics `k` is pre-decided.
- A document is a probability distribution of topics, and every topic is a probability distribution of words.
- What LDA does is that when you fit it with all available documents, it is trying its best to find the best topic mix and the best word mix.

### Further assumptions of LDA for Topic Modelling:
- Documents with similar topics use similar groups of words
- Latent topics can then be found by searching for groups of words that frequently occur together in documents across the corpus
- Documents are probability distributions over latent topics which signifies certain document will contain more words of a specific topic.

## Limitations
- LDA has fixed number of `k`. This means that the number of topics is fixed and must be known ahead of time. Also, there is limit to amount of topics we can generate.
- Topics are uncorrelated because **Dirichlet Topic Distribution** cannot capture correlations.
- LDA is Non-hierarchical. In data-limited regimes hierarchical models allow sharing of data.
- It is static therefore there is no evolution of topics over time.
- Makes use of **Bag-of-Words** approach. LDA assumes words are exchangeable and sentence structure is not modelled.
- LDA is weakly unsupervised. Sometimes some supervision is desirable, e.g. in sentiment analysis.

### References:
Some useful and not very technical references can be found [here](https://scikit-learn.org/stable/modules/decomposition.html#latentdirichletallocation), [here](https://arxiv.org/pdf/1405.0099.pdf) and [here](https://towardsdatascience.com/latent-dirichlet-allocation-lda-9d1cd064ffa2).