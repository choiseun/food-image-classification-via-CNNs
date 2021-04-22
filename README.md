# Food Image Classification via CNNs

---

### Technology & Skills

**Technology** Python, Jupyter Notebook, GitHub, Git

**Python Libraries:** Pandas, requests, time, urllib, sys, os, numpy, tensorflow, keras, scikit-learn, matplotlib

**Technical Skills:** Multiclass classification, data collection, data cleaning, scraping web API, image processing, pre-processing, modeling, data visualization, exploratory data analysis (EDA), computer vision, deep learning, convolutional neural networks, neural network architecture, image data augmentation, accuracy, precision, recall, confusion matrix, pre-trained model, transfer learning, bias-variance tradeoff

**Models:** Convolutional neural network, ResNet50, EfficientNet-B0

---

### Overview

This project will cover the following:
- Problem Statement
- Executive Summary
- Conclusion
- Data Sources
- Data Dictionary

---

### Problem Statement

In this project, I intend on building a convolutional neural network (CNN) to classify food images.

In this project, I hope to accomplish the following objectives:
- Collect and clean at least 200 images per food class for 5 classes using the pushshift.io Reddit API, and
- Build convolutional neural networks from scratch and pre-trained, state of the art models to predict multiclass food classes with accuracy scores higher than that of the null model.

For this multiclass classification problem, I aim to predict the following 5 classes:
1. Hamburger
2. Hot dog
3. Pizza
4. Taco
5. Sushi

I will be using the following subreddits to collect image data:
- r/burgers (103k members)
- r/hotdogs (19.5k members)
- r/Pizza (309k members)
- r/tacos (47.7k members)
- r/sushi (226k members)

The general workflow is as follows: image data --> multiclass outcome.

---

### Executive Summary

Using fewer than 300 images per class, my production model achieved an accuracy of 64.78% on unseen data for a multiclass image classification problem. The convolutional neural network made from Google's pre-trained EfficientNet-B0 model utilized image data augmentation to enhance its performance. The model performed the best when predicting pizza and sushi and performed the worst at predicting sushi. I also implemented IBM's pre-trained ResNet50 model in a transfer learning environment, but the model failed to achieve a higher validation accuracy than the production model in the designated 25 epochs.

---

### Conclusion

In this project, I built numerous convolutional neural networks to predict multiple food classes for image data. While there were certainly many roadblocks that affected the scope of the project, such as computing power and a small dataset, I managed to develop a production model that could handily beat the null model on validation accuracy and gained insight into model performance and architecture. With more time and resources, the project can be expanded to achieve more useful applications. Regardless, this was a fun introduction to convolutional neural networks for image processing.

**Next Steps:** 

If expanded, this project can adopt multiple practical applications.

If one were interested in a recipe recommender system, the user would provide the model with an image of ANY food in existence, and the model would accurately predict the name of the food and provide a generic recipe that details the ingredients and steps for preparing the food. This would be a useful tool for anyone trying a new dish/cuisine or people with specific dietary restrictions. 

If taken even further, the project could perform a similar function for any image object and provide a prediction for an unidentified object. This would be extremely helpful for those who are visually impaired.

A third potential application would be to create a dinner recommender system. Based on the user's preference for a similar or dissimilar food class, the user would pass in a food image, and the recommender system would suggest options for dinner that resemble or differ to a specified degree from the provided image.

---

### Data Sources

Given more resources, the optimal way to collect image data would have been through a web API for Google Images. Unfortunately, this would have required securing a bigger budget and navigating the nuances of the /robots.txt page for Google Images (which is very particular about what is and is not allowed). Thus, for practical reasons, I chose to collect the image data using the pushshift.io Reddit API. The links to the data have been provided below:
- [r/burgers](https://api.pushshift.io/reddit/search/submission?subreddit=burgers): The pushshift.io Reddit API for r/burgers.
- [r/hotdogs](https://api.pushshift.io/reddit/search/submission?subreddit=hotdogs): The pushshift.io Reddit API for r/hotdogs.
- [r/Pizza](https://api.pushshift.io/reddit/search/submission?subreddit=Pizza): The pushshift.io Reddit API for r/Pizza.
- [r/tacos](https://api.pushshift.io/reddit/search/submission?subreddit=tacos): The pushshift.io Reddit API for r/tacos.
- [r/sushi](https://api.pushshift.io/reddit/search/submission?subreddit=sushi): The pushshift.io Reddit API for r/sushi.

---

### Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|subreddit|object|df|The name of the subreddit|
|title|object|df|The contents of the post|
|url|object|df|The url for the image|

---