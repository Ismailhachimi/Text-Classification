
# Comparative Study of CNN and RNN for Arabic TextClassification

**Under supervision of Mr. [Stéphane Canu](https://scholar.google.fr/citations?user=PpibCZUAAAAJ&hl=fr&oi=ao)**

This project is a step towards understanding the state of the art of text classification in deep learning. As a result, we compare CNN and RNN to understand the pros and cons of each architecture. 

## Project Plan
1. [Introduction](#1-introduction)
2. [State of the art](#2-state-of-the-art)
    1. [Word representation](#i-word-representation)
    2. [Text classification](#ii-text-classification)
3. [Data for Arabic text classification](#3-data-for-arabic-text-classification)
4. [Implementation and results](#4-implementation-and-results)
5. [Perspectives](#5-perspectives)
6. [Conclusion](#6-conclusion)
7. [Bibliography](#7-bibliography)

## 1. Introduction

This project is an assembly of research and learning processes which aims to understand the state-of-the-art of text classification in deep learning as it requires us to look for a relevant data source, go through word representation models and compare them as a first step. In the second phase, we compare text classification based technologies and we try to understand how they work. Finally, we explain in detail text classification in deep learning and propose an attention-based architecture as a result of this project.

## 2. State of the art

### i. Word representation

Word representation is a major change in NLP research due to its great help in late advances in different problems related to text analysis for specific topic : Text classification, Topic modeling, intention recognition etc.

In this project, we try to elaborate the state of the art of text classification in Arabic using language models and deep learning. The use of language models is due to simplicity of intergration in a neural network and its intuition of representiong words in a vectorial space which helps calculating dependencies between words.

The main state of the art Word Representation models are : 

>	- [Word2Vec](https://arxiv.org/pdf/1310.4546) (2013)
>	- [GloVe](https://nlp.stanford.edu/pubs/glove.pdf) (2015)
>	- [FastText](https://arxiv.org/pdf/1607.04606) (2017)
>	- [ELMo](https://arxiv.org/pdf/1802.05365) (2018)

For the first part, we use a pretrained language model Word2Vec taken from this [Github Repository](https://github.com/bakrianoo/aravec) as a result of research paper mentioned in [Citation](#Citation). Thanks [bakrianoo - Abu Bakr Soliman](https://github.com/bakrianoo).

#### Citation

> Abu Bakr Soliman, Kareem Eisa, and Samhaa R. El-Beltagy, “AraVec: A set of Arabic Word Embedding Models for use in Arabic NLP”, in proceedings of the 3rd International Conference on Arabic Computational Linguistics (ACLing 2017), Dubai, UAE, 2017.

### ii. Text classification

In this part, we explain the state-of-the-art of text classification in deep learning by going through the relevant research result of previous years.

## 3. Data for Arabic text classification

In this part, we cite text data that we choosed to train our text classification model using Word2Vec word embedding model as marked in this [Section](#i-word-representation).

The dataset is a collection of Arabic texts, which covers modern Arabic language used in newspapers articles. For this, we thank Mohamed BINIZ for making it available.

#### Citation

> Mohamed, BINIZ (2018), “DataSet for Arabic Classification”, Mendeley Data, v2
> [DOI](http://dx.doi.org/10.17632/v524p5dhpj.2)
> Dataset: DataSet for Arabic Classification

## 4. Implementation and results

## 5. Perspectives

As future work, we plan to focus on Attention Models using CNN. 

## 6. Conclusion

A brief resume on the work during the project period, the achieved results and the future advances that might be applied to improve our solution.

## 7. Bibliography

> [1]  Piotr Bojanowski, Edouard Grave, Armand Joulin, and Tomas Mikolov. Enriching word vectors with subword information. arXiv preprint arXiv:1607.04606, 2016. 
>
> [2]  Junyoung Chung, Caglar Gulcehre, KyungHyun Cho, and Yoshua Bengio. Empirical evaluation of gated recurrent neural networks on sequence modeling. arXiv preprint arXiv:1412.3555, 2014. 
>
> [3]  Jeffrey L Elman. Finding structure in time. Cognitive science, 14(2):179–211, 1990. 
>
> [4]  Sepp Hochreiter and Jürgen Schmidhuber. Long short-term memory. Neural computation, 9(8):1735–1780, 1997. 
>
> [5]  Yann LeCun, Léon Bottou, Yoshua Bengio, and Patrick Haffner. Gradient-based learning applied to document recognition. Proceedings of the IEEE, 86(11):2278–2324, 1998. 
>
> [6]  Tomas Mikolov, Ilya Sutskever, Kai Chen, Greg S Corrado, and Jeff Dean. Distributed representations of words and phrases and their compositionality. In Advances in neural information processing systems, pages 3111–3119, 2013. 
>
> [7]  Jeffrey Pennington, Richard Socher, and Christopher Manning. Glove: Global vectors for word representation. In Proceedings of the 2014 conference on empirical methods in natural language processing (EMNLP), pages 1532–1543, 2014.
