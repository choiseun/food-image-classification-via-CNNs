# Recipe Recommender System

---

### Technology & Skills

**Technology** Python, Jupyter Notebook, GitHub, Git

**Python Libraries:** Pandas, requests, time, urllib, sys, os, tensorflow (keras), scikit-learn, numpy, matplotlib

**Technical Skills:** Multiclass classification, data collection, data cleaning, scraping web API, deep learning, convolutional neural networks, image processing, computer vision, transfer learning, pre-trained model, confusion matrix, image data augmentation

**Models:** Convolutional neural network, ResNet50, EfficientNet

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

In this project, I intend on taking images of food, building a convolutional neural network (CNN) for image classification, and then recommending a generic recipe that details the ingredients and steps for preparing the dish.

In this project, I hope to accomplish the following objectives:
- Collect and clean at least 200 images per food class for 5 classes using the pushshift.io Reddit API,
- Build a convolutional neural network from scratch to predict multiclass food classes with accuracy, precision, and recall scores that beat those of the null model, and
- Recommend a recipe based on the predicted food class so that the user can understand the basic ingredients and process of food preparation required to make the dish.

For this multiclass classification problem, I aim to predict the following 5 dishes:
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

The general workflow is as follows: image data --> multiclass outcome --> recipe.

---

### Executive Summary

Using fewer than 300 images per class, my production model achieved an accuracy of 54.93% on unseen data for a multiclass image classification problem. Altogether, the convolutional neural network made from scratch had 15 layers (including the input and output layers) and utilized image data augmentation to enhance its performance. The model performed the best when predicting pizza and performed the worst when predicting tacos when the image was actually a hotdog. I also implemented IBM's pre-trained ResNet50 model in a transfer learning environment, but the model did not achieve a higher validation accuracy than the production model in the designated 20 epochs.

---

### Conclusion

In this project, I built numerous convolutional neural networks to predict multiple food classes for image data. While there were certainly many roadblocks that affected the scope of the project, such as computing power and a small dataset, I managed to develop a production model that could handily beat the null model on validation accuracy and gained insight into model performance and architecture. With more time and resources, the project can be expanded to achieve more useful applications. Regardless, this was a fun introduction to convolutional neural networks for image processing.

**Next Steps:** If expanded, this project can adopt multiple practical applications.

If one were interested in the ability to convert images to text or a recommender system, the project could become somewhat of a reverse Google Images. In the context of this project, the user would provide the model with an image of ANY food in existence, and the model would accurately predict the name of the food and provide a recipe that details the ingredients and steps for preparing the food. This would be a useful tool for anyone trying a new dish or cuisine or people with specific dietary restrictions. If taken even further, the project could perform a similar function for any image object and provide a recommendation based on the prediction.

Another potential application would be to create a dinner recommendation system. Based on the user's preference for a similar or dissimilar food class, the user would pass in a food image, and the recommender system would suggest options for dinner that resemble or differ from the input.

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