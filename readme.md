
# Text Classification With Attention-based Neural Networks

**Under supervision of Mr. [Stéphane Canu](https://scholar.google.fr/citations?user=PpibCZUAAAAJ&hl=fr&oi=ao)**

This project is a step towards understanding the state of the art of text classification in deep learning. As a result, we propose an attention-based architecture as a contribution.

## Project Plan
1. [Introduction](#1-introduction)
2. [State of the art](#2-state-of-the-art)
    1. [Word representation](#i-word-representation)
    2. [Text classification](#ii-text-classification)
    	1. [Text classification technologies](#a-text-classification-technologies-)
    	2. [Text classification in Deep Learning](#b-text-classification-in-deep-learning-)
3. [Getting data](#3-getting-data)
    1. [Audio data and Google Cloud Speech](#i-audio-data-and-google-cloud-speech)
    2. [Comparison of word representation models](#ii-comparison-of-word-representation-models)
4. [A text classification architecture](#4-a-text-classification-architecture)
    1. [An overview of the solution](#i-an-overview-of-the-solution)
    2. [Implementation and results](#ii-implementation-and-results)
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

#### a. Text classification technologies : 

Today's technologies are a sort of dialog generation systems that offer a new type of user experience. Many technologies like Google's Assistant Bot, helps users to get their needs by offering automated tasks, supervision and dialog experience. Thus, a text classifier is an important component to achieve this. In fact, in order to execute a specific task, a component takes care of this task by mapping the input text from user's expression (which embeds a speech-to-text part) to a pre-defined task. For example : asking Amazon's virtual assistant Alexa to set the alarm on a specific time.

To learn more about these systems, we will deploy on each of the following technologies a model to quantify the capacity of each one :

>   - Watson Knowledge Studio 
>   - Alexa Skills Kit 
>   - Google's DialogFlow

All these technologies offer a free limited account.

#### b. Text classification in deep learning :

In this part, we explain the state-of-the-art of text classification in deep learning by going through the relevant research result of previous years.

## 3. Getting data

### i. Audio data and Google Cloud Speech

In this part, we introduce Google Cloud API, which is a component of Google Cloud Platform. We use google speech API in order to map audio data to text data after scraping [this website](http://www.archives-manche.fr) which contains archives of old spoken french audio about many topics.

For this section, we need to :

	- Scrape Text data from the said website
	- Make a volumetric analysis report on the audio data


### ii. Comparison of Word representation models

In this part, we : 

	- reproduce the state-of-the-art word representation models
	- compare the resulting models 

## 4. A text classification architecture

### i. An overview of the solution

### ii. Implementation and results

## 5. Perspectives

In this chapter, we proposed more ideas for future work on this project. 

## 6. Conclusion

A brief resume on the work during the project period, the achieved results and the future advances that might be applied to improve our solution.

## 7. Bibliography

> [References]
