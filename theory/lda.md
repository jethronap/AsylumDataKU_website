# Latent Dirichlet Allocation (LDA):


Probabilistic, generative model which uncovers the topics latent to a dataset by assigning weights to words in a corpus, where each topic will assign different probability weights to each word.

For a given corpus, a topic model estimates a topic distribution for each of its documents (i.e., a a distribution of weights over a set of topics), where a topic is itself a distribution of weights over the vocabulary of the corpus. The most weighted words of each topic are syntactically and/or semantically related, given that collection of documents. This means that two distinct topics share the exact same vocabulary, but have different weight distributions.

The LDA algorithm first models documents via a mixture model of topics. From these topics, words are then assigned weights based on the probability distribution of these topics. It is this probabilistic assignment over words that allow a user of LDA to say how likely a particular word falls into a topic. Subsequently from the collection of words assigned to a particular topic, are we thus able to gain an insight as to what that topic may actually represent from a lexical point of view.

REFs here [1](https://scikit-learn.org/stable/modules/decomposition.html#latentdirichletallocation) and [2](https://arxiv.org/pdf/1405.0099.pdf).

**Assumptions**:

- Each document is just a collection of words or a “bag of words”. Thus, the order of the words and the grammatical role of the words (subject, object, verbs, …) are not considered in the model.
- Words like am/is/are/of/a/the/but/… don’t carry any information about the “topics” and therefore can be eliminated from the documents as a preprocessing step. In fact, we can eliminate words that occur in at least %80 ~ %90 of the documents, without losing any information. For example, if our corpus contains only medical documents, words like human, body, health, etc might be present in most of the documents and hence can be removed as they don’t add any specific information which would make the document stand out.
- We know beforehand how many topics we want. ‘k’ is pre-decided.
- All topic assignments except for the current word in question are correct, and then updating the assignment of the current word using our model of how documents are generated

REFS [1](https://towardsdatascience.com/latent-dirichlet-allocation-lda-9d1cd064ffa2)

- A document is a probability distribution of topics, and every topic is a probability distribution of words.
- What LDA does is that when you fit it with all those document, it is trying its best to find the best topic mix and the best word mix.

Further assumptions of LDA for Topic Modelling:
- Documents with similar topics use similar groups of words
- Latent topics can then be found by searching for groups of words that frequently occur together in documents across the corpus
- Documents are probability distributions over latent topics which signifies certain document will contain more words of a specific topic.

**Limitations**:
- Fixed K (the number of topics is fixed and must be known ahead of time) There is limit to amount of topics we can generate
- Uncorrelated topics (Dirichlet topic distribution cannot capture correlations)
- Non-hierarchical (in data-limited regimes hierarchical models allow sharing of data)
- Static (no evolution of topics over time)
- Bag of words (assumes words are exchangeable, sentence structure is not modelled)
- Unsupervised (sometimes weak supervision is desirable, e.g. in sentiment analysis)