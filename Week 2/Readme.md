## Manually implement the TF-IDF algorithm and comparision of results with the outputs from scikit-learn's `CountVectorizer` and `TfidfVectorizer`.

During Manual implementation of TF-IDF Algorithm, the formula that i have used to compute IDF is:    
    
```**IDF(t) = log10(N/ (1 + DF(t)) )**```     
where N = Number of documents in the corpus    
and DF(t)= Number of Documents in Corpus containing word term.    

And Term frequency of term t = TF(t) is defined as:     
    
```**TF(t) = Number of times term t appear in document/ Words Count in a document**```    
And TF-IDF is defined as: ```**TF(t)*IDF(t)**```    

In case of  ```CountVectorizer```, it generate a sparse matrix of dimension:    
***(num_documents, num_words)***         
Where num_documents = number of Documents in Corpus    
and num_words = number of Words in vocabulary which is created from entire Corpus     


>[!Note]    
```CountVectorizer``` is similar to computing TF but it does not normalise the count of a particular term from a document, also it ***ignore individual letters, punctuation and numbers (default) while creating the vocabulary***, it can also ignore stop words but need to be explicitly mentioned in parameters to it.


>[!Note]
```TfidfVectorizer``` in sklearn is also similar to what i have implemented, additionally is also ***ignore individual letters, punctuation and numbers (default) while creating the vocabulary***,  it can also ignore stop words but need to be explicitly mentioned in parameters to it.    
Additionally **IDF** in ```TfdifVecotizer``` is defined as:    
```**IDF(t) = log(N +1/ (1 + DF(t)) ) + 1**```    
and **by default, it applies L2 normalization row-wise after computing the TF-IDF matrix.**    
Such that the final document Vector is normalised as:    
```**v_normalized = v / ||v||₂**```
