---
title: What is the Computer Vision API? - Computer Vision
titlesuffix: Azure Cognitive Services
description: The Computer Vision service provides developers with access to advanced algorithms for processing images and returning information. 
services: cognitive-services 
author: PatrickFarley
manager: cgronlun

ms.service: cognitive-services 
ms.subservice: computer-vision 
ms.topic: overview
ms.date: 08/22/2018 
ms.author: pafarley
ms.custom: seodec18
#Customer intent: As a developer, I want to evaluate image processing functionality, so that I can determine if it will work for my information extraction or object detection scenarios.
---
# What is Computer Vision?

The cloud-based Computer Vision service provides developers with access to advanced algorithms for processing images and returning information. Computer Vision works with popular image formats, such as JPEG and PNG. To analyze an image, you can either upload an image or specify an image URL. Computer Vision algorithms can analyze the content of an image in different ways, depending on the visual features you're interested in. For example, Computer Vision can determine if an image contains adult or racy content, or find all the faces in an image.

You can use Computer Vision in your application, by either using our [client libraries](quickstarts-sdk/csharp-analyze-sdk.md) to invoke the service, or invoking the [REST API](vision-api-how-to-topics/howtocallvisionapi.md) directly, to:

- [Analyze images for insight](#analyzing-images-for-insight)
- [Extract text from images](#extracting-text-from-images)
- [Moderate content in images](#moderating-content-in-images)

## Analyzing images for insight

You can analyze images using Computer Vision to detect and provide insight about the visual features and characteristics of your images. You can either upload the contents of an image to analyze local images, or you can specify the URL of an image to analyze remote images.

Computer Vision can do the following actions when analyzing an image:

| Action | Description |
| ------ | ----------- |
|**[Tag visual features](concept-tagging-images.md)**|Identify and tag visual features in an image, from a set of thousands of recognizable objects, living things, scenery, and actions. When the tags are ambiguous or not common knowledge, the API response provides 'hints' to clarify the meaning of the tag in the context of a known setting. Tagging isn't limited to the main subject, such as a person in the foreground, but also includes the setting (indoor or outdoor), furniture, tools, plants, animals, accessories, gadgets, and so on.|
|**[Detect objects](concept-object-detection.md)**| Object detection is similar to tagging, but the API returns the bounding box coordinates for each tag applied. For example, if an image contains a dog, cat and person, the Detect operation will list those objects together with their coordinates in the image. You can use this functionality to process further relationships between the objects in an image. It also lets you know when there are multiple instances of the same tag in an image.|
|**[Categorize an image](concept-categorizing-images.md)**|Identify and categorize an entire image, using a [category taxonomy](Category-Taxonomy.md) with parent/child hereditary hierarchies. Categories can be used alone, or with our new tagging models.<br/>Currently, English is the only supported language for tagging and categorizing images.|
|**[Describe an image](concept-describing-images.md)**|Generate a description of an entire image in human-readable language, using complete sentences. Computer Vision's algorithms generate various descriptions based on the objects identified in the image. The descriptions are each evaluated and a confidence score generated. A list is then returned ordered from highest confidence score to lowest.|
|**[Detect faces](concept-detecting-faces.md)** |Detect faces in an image and provide information about each detected face. Computer Vision returns the coordinates, rectangle, gender, and age for each detected face.<br/>Computer Vision provides a subset of the functionality that can be found in [Face](/azure/cognitive-services/face/), and you can use the Face service for more detailed analysis, such as facial identification and pose detection.|
|**[Detect image types](concept-detecting-image-types.md)**|Detect characteristics about an image, such as whether an image is a line drawing or the likelihood of whether an image is clip art.|
|**[Detect domain-specific content](concept-detecting-domain-content.md)**|Use domain models to detect and identify domain-specific content in an image, such as celebrities and landmarks. For example, if an image contains people, Computer Vision can use a domain model for celebrities included with the service to determine if the people detected in the image match known celebrities.|
|**[Detect the color scheme](concept-detecting-color-schemes.md)**|Analyze color usage within an image. Computer Vision can determine whether an image is black & white or color and, for color images, identify the dominant and accent colors.|
|**[Generate a thumbnail](concept-generating-thumbnails.md)**|Analyze the contents of an image to generate an appropriate thumbnail for that image. Computer Vision first generates a high-quality thumbnail and then analyzes the objects within the image to determine the *area of interest*. Computer Vision then crops the image to fit the requirements of the area of interest. The generated thumbnail can be presented using an aspect ratio that is different from the aspect ratio of the original image, depending on your needs.|
|**[Get the area of interest](concept-generating-thumbnails.md#area-of-interest)**|Analyze the contents of an image to return the coordinates of the *area of interest*. This is the same function that is used to generate a thumbnail, but instead of cropping the image, Computer Vision returns the bounding box coordinates of the region, so the calling application can modify the original image as desired.|

## Extracting text from images

You can use Computer Vision to [extract text using OCR](concept-extracting-text-ocr.md) from an image into a machine-readable character stream. If needed, OCR corrects the rotation of the recognized text, in degrees, around the horizontal image axis, and provides the frame coordinates of each word. OCR supports 25 languages, and automatically detects the language of extracted text.

You can also [recognize printed and handwritten text](concept-recognizing-text.md) from an image. Computer Vision can detect and extract both printed and handwritten text from images of various objects with different surfaces and backgrounds, such as receipts, posters, business cards, letters, and whiteboards. Currently, recognizing printed and handwritten text is in preview, and English is the only supported language.  

## Moderating content in images

You can use Computer Vision to [detect adult and racy content](concept-detecting-adult-content.md) in an image, rating the likelihood that the image contains either adult or racy content and generating a confidence score for both. The filter for adult and racy content detection can be set on a sliding scale to accommodate your preferences.

## Using containers

[Use Computer Vision containers](computer-vision-how-to-install-containers.md) to recognize printed and handwritten text locally, by installing a standardized Docker container closer to your data.

## Image requirements

Computer Vision can analyze images that meet the following requirements:

- The image must be presented in JPEG, PNG, GIF, or BMP format
- The file size of the image must be less than 4 megabytes (MB)
- The dimensions of the image must be greater than 50 x 50 pixels  
  For OCR, the dimensions of the image must be between 50 x 50 and 4200 x 4200 pixels

## Data privacy and security

As with all of the Cognitive Services, developers using the Computer Vision service should be aware of Microsoft's policies on customer data. See the [Cognitive Services page](https://www.microsoft.com/trustcenter/cloudservices/cognitiveservices) on the Microsoft Trust Center to learn more.

## Next steps

Get started with Computer Vision with one of our quickstarts:

- [Analyze an image](quickstarts-sdk/csharp-analyze-sdk.md)
- [Extract handwritten text](quickstarts-sdk/csharp-hand-text-sdk.md)
- [Generate a thumbnail](quickstarts-sdk/csharp-thumb-sdk.md)
