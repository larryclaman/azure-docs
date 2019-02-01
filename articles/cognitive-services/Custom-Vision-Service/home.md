---
title: What is Azure Custom Vision?
titlesuffix: Azure Cognitive Services
description: Learn how to use the Custom Vision service to build custom image classifiers in the Azure cloud.
services: cognitive-services
author: anrothMSFT
manager: cgronlun

ms.service: cognitive-services
ms.subservice: custom-vision
ms.topic: overview
ms.date: 01/10/2019
ms.author: anroth
#Customer intent: As a data scientist/developer, I want to understand what the Custom Vision service does so that I can determine if it's suitable for my project.
---
# What is Azure Custom Vision?

The Azure Custom Vision API is a cognitive service that lets you build, deploy and improve custom image classifiers. An image classifier is an AI service that sorts images into classes (tags) according to certain characteristics. Unlike the [Computer Vision](https://docs.microsoft.com/azure/cognitive-services/computer-vision/home) service, Custom Vision allows you to create your own classifications.

## What it does

The Custom Vision service uses a machine learning algorithm to classify images. You, the developer, must submit groups of images that feature and lack the classification(s) in question. You specify the correct tags of the images at the time of submission. Then, the algorithm trains to this data and calculates its own accuracy by testing itself on that same data. Once the model is trained, you can test, retrain, and eventually use it to classify new images according to the needs of your app. You can also export the model itself for offline use.

### Classification and object detection

Custom Vision functionality can be divided into two features. **Image classification** assigns a distribution of classifications to each image. Both multiclass (one tag per image) and multilabel (any number of tags per image) classification models are supported. **Object detection** is similar to multilabel classification, but it also returns the coordinates in the image where the applied labels can be found.

### Optimization

In general, the methods that the Custom Vision service uses are robust to differences, which allows you to start prototyping with a small amount of data. 50 images per tag are generally a good start. This means, however, that the service is not optimal for detecting subtle differences in images (for example, detecting minor cracks or dents in quality assurance scenarios).

Additionally, you can choose from several varieties of the Custom Vision algorithm that are optimized for certain subject material&mdash;for example, landmarks or retail items. See the [Build a classifier](getting-started-build-a-classifier.md) guide for more information on these.

## What it includes
The Custom Vision Service is available as a set of native SDKs as well as through a web-based interface on the [Custom Vision home page](https://customvision.ai/). You can create, test, and train a model through either interface, or both.

![Custom Vision home page in a Chrome browser window](media/browser-home.png)

## Data privacy and security

As with all of the Cognitive Services, developers using the Custom Vision service should be aware of Microsoft's policies on customer data. See the [Cognitive Services page](https://www.microsoft.com/trustcenter/cloudservices/cognitiveservices) on the Microsoft Trust Center to learn more.

## Next steps

Follow the [Build a classifier](getting-started-build-a-classifier.md) guide to get started using Custom Vision on the web, or complete an [Image classification tutorial](csharp-tutorial.md) to implement the scenario in code.
