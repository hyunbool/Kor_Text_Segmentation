# Korean Semantic Text Segmentation with Embeddings

A Korean Version of [Semantic Text Segmentation with Embedding](https://github.com/ReemHal/Semantic-Text-Segmentation-with-Embeddings)

## Introduction

Given a text document *d* and a desired number of segments *k*, 
this repo shows how to segment the document into *k* semantically homoginuous segments. 

The general approach is as follows:
1. Convert the words in *d* into embedding vectors using the GloVe model.
2. For all word sequences *s* in *d*: the average meaning (centroid) of *s* is represented by taking the average embeddings of all words in *s*.
3. The error in the centroid calculation for a sequence *s* is calculated as the average cosine distance between the centroid and all words in *s*.
4. The segmentation is done using the greedy heuristic by iteratively choosing the best split point *p*.


The class text_segmentation_class in __[text_segmetnation.py](https://github.com/ReemHal/Semantic-Text-Segmentation-with-Embeddings/blob/master/text_segmentation.py)__ contains funtions to convert the document
words in GloVe embeddings and choose the splitting points. The notebook __[semantc_text_segmentation_example.ipynb](https://github.com/ReemHal/Semantic-Text-Segmentation-with-Embeddings/blob/master/semantc_text_segmentation_example.ipynb)__
demonstrates how to use the class.

<a name="tech"><a/>

## Embeddings

1) https://github.com/ratsgo/embedding/releases 에서 제공하는 word-embeddings.zip 중 glove 사용

2) https://github.com/jroakes/glove-to-word2vec/blob/master/convert.py 이용해 glove => word2vec

* 일단 원작자도 glove를 사용했길래 일단 이렇게 했는데... word2vec으로 다시 시도해보기

