# ABMile
<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>
## ToC
- [Overview](#overview)
- [Run](#run)
- [Solution](#Solution)


## Overview

Alfabeto is a Python3 program with the aim of checking a text language (between english and italian). The main idea is to underly the languages sounds through network theory and generalize thanks to machine learning algorithms.


## Run

Download Alfabeto2.0 ipython notebook from GitHub repository.
Code is written in Python 3 and it requires the following libraries: networkx sklearn. 


## Solution

Language's sounds are treated as near letters in a word, e.g. in the word "Alfabeto" we have the following "links": (a,l), (l,f), (f,a), et cetera. We convert this idea into a weighted network, where links are as descrbed above and the number of times a link appears is its weght. In this way we can create a network for a general text and plot it converting the links' weights into distances i.e. if two letters are usually closed each other in the text, they will be near in the network plotting. The following plots are for an english text network and an italian text netowrk respectively:

![network1][network1]
![network2][network2]

Studying the network we can calculate the following quantities: degree distribution, clustering coefficient, assortative coefficient, et cetera. We filter them in order to have only usefull quantities in the aim of discriminating two texts. Then we use them as features of a machine learning algorithm. 

In particular we generate two groups of artificial texts (ENG, ITA) by taking at random from an english and italian dictionary (respectively) some words. We calculate the usefull network quantities and assign them as features vector, then we add the right language label (ENG/ITA), according to its creation. This is he training set.

Then we use a Naive-Bayes ML model fitting it on the training set (more than 200 texts: half in english and half in italian). The prediction is done in two real english and italian texts giving a correct discrimination.

