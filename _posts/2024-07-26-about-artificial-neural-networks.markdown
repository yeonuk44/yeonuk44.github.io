---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_About_Artificial_Neural_Networks
title: About artificial neural networks
# title: About artificial neural networks
# if not specified, .name will be used from _data/owner/[language].yml
author: Yeonuk
# multiple category is not supported
category: Statistics
# multiple tag entries are possible
tags: [statistics]
# thumbnail image for post
img: ":post_pic1.jpg"
# disable comments on this page
# comments_disable: true

# publish date
date: 2024-07-26 09:00:00 +0900
# seo
# if not specified, date will be used.
#meta_modify_date: 2021-08-10 11:32:53 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# please use the "image_viewer_on" below to enable image viewer for individual pages or posts (_posts/ or [language]/_posts folders).
# image viewer can be enabled or disabled for all posts using the "image_viewer_posts: true" setting in _data/conf/main.yml.
#image_viewer_on: true
# please use the "image_lazy_loader_on" below to enable image lazy loader for individual pages or posts (_posts/ or [language]/_posts folders).
# image lazy loader can be enabled or disabled for all posts using the "image_lazy_loader_posts: true" setting in _data/conf/main.yml.
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---

<!-- outline-start -->

## This is an article about artificial neural networks.

Hello!

Today, we're going to learn about artificial neural networks.

Artificial neural networks (ANNs) are machine learning models inspired by the neuronal system of the human brain and are used to learn and predict complex nonlinear relationships.

{:data-align="center"}

<!-- outline-end -->

## the main concept

### Neuron

Artificial neural networks are models of artificially implemented neurons that receive inputs, multiply weights, and generate outputs through activation functions.

### Hidden Layer

A layer located between the input layer and the output layer, used to learn nonlinear relationships in the input data.

### Weight

A parameter that represents the importance given to the connection between the input and hidden layers and the hidden and output layers.

## principle of operation

### 순전파(Forward Propagation)

The process by which the input data passes through a neural network and propagates to the output layer, the output is calculated through the weight and activation function of each layer.

### 역전파(Backward Propagation)

The process of calculating the error between the output and the actual value and propagating the error in reverse to the weight of each layer to adjust the weight.

## a major algorithm

### Multilayer Perceptron (MLP)

A neural network with multiple layers of concealment, used to solve complex nonlinear problems.

### Convolutional Neural Network (CNN)

A neural network specialized in image classification, object detection, and image processing, used to learn local information through convolution and pooling.

### Recurrent Neural Network (RNN)

It is used to model ordered data (time series data, natural language, etc.), and is effective in maintaining ordered information through memory structures.

## Utilization

### Image recognition

CNN performs tasks such as face recognition, object detection, etc.

### Natural language processing

It utilizes RNNs for machine translation, sentence generation, emotional analysis, etc.

### financial projections

It is used for stock price prediction and time series data analysis.

## Precautions

### overfitting

In large neural networks, attention should be paid to overfitting problems.

### Adjusting Hyperparameters

Since the performance of neural networks is heavily influenced by various hyperparameters, appropriate adjustments are required.

## at the end of the day

Artificial neural networks are utilized in a variety of fields and are effectively used to solve complex and nonlinear problems.

Thank you!
