# Fake_News_Prediction

[Click here for the full report](https://github.com/ashishvinodkumar/Fake_News_Prediction/blob/main/30_Report/Final_Report.pdf)

# Abstract
Fake News has recently become a buzzword describing lies and false information spread through news outlets and social media.  Many have sought to find ways to classify news articles and headlines as either fake news or accurate information.  This paper aims to explore Convolutional Neural Networks as a classification tool for the Liar dataset created by William Yang Wang.  To test our dataset we used word embeddings on the text of our labeled dataset.  Both our regression and neural network are multi-class models because our data is labeled with one of six categories from “completely false” to “completely true”.  We were able to achieve similar results as reported by William Yang Wang in the original Liar dataset paper.  Our Convolutional Neural network achieved 21% accuracy and our Logistic Regression achieved 25% accuracy. Our results demonstrate the importance of model comparison, the strength of logistic regressions, and the difficulty of multi-class models.  

# Introduction
In this project, we will try to utilize the Logistic Regression (LR) model and the Convolutional neural networks (CNN) model to replicate the results in the article written by Wang(2017) by using the LIAR dataset. Specifically, this paper is organized as follows: the background section examines the literature in the field of fake news detection and also introduces the LIAR dataset. The methodology section describes the data processing approach, the LR model, and the CNN model. In the results section, we compare and interpret the metrics from those two models. Finally, current limitations of models’ application and possible directions for further improvements are discussed at the last Section.

# Result
The overall model accuracy for the multi-class logistic regression model was 25%. The precision score was 26%, recall score was 22.6%, along with an F1 score of 22.1%.

Interestingly, having a multi-class response variable reduces the model accuracy as the words that identify completely true are similar to the words that identify half-true. This is true not just for the true label statements, but also for the false label statements. This overlap of words results in no clear delineation between two levels, thus severely reducing our model accuracy, precision and recall. 

To further test this hypothesis, we proceeded to bucket the 6 labels into broader labels of simply consisting of False and True. We immediately noticed that the overall model accuracy increased to 62.8%. The precision score increased to 65%, recall score to 75.1%, and F1 score increased to 69.7%. 

Here is a plot of the ROC curve that showcases an AUC of 65.1% when we have a binary response label instead of a multi-class label.





Convolutional Neural Network performed with an accuracy of 21% on our separated test data.  In the figures below we see graphs of the model’s accuracy and the model’s loss.  Our model reached epoch 6 before it began overfitting.  

Though the LIAR dataset is larger than any other fake news classification dataset, it may still not be large enough to expect fine tuned results from a Convolutional Neural Network.  A larger dataset would improve our accuracy and ability to classify fake news.  We also note that our model struggled to accurately detect all 6 categories of Fake News.  Bucketing the six categories of truthfulness into “True” and “False” may also improve the accuracy and performance of our model, as it did with our Logistic Regression.  However, the number of labels could be dependent on the use case.

Overall, our Convolutional Neural Network’s accuracy was comparable to the original paper’s CNN accuracy of 27%.  It is important to remember that our inaccurate predictions may have been the result of a one-category mis-step (for example, the difference between “half-true” and “completely true”), while maintaining the overall sentiment of a text. We are confident that adding other layers, feeding the model more predictors, or reducing the classification task would improve our model’s accuracy.


# Conclusion
Using the LIAR dataset, the LR model and the CNN model, this short paper tried to replicate the results generated by William Yang Wang in his article. We found a similar accuracy for the prediction by using the LR model, however, we did not achieve the exact same accuracy like what the paper shows by using the specific CNN model we used. We noticed that the dataset could be the cause of the relatively low accuracy we got with the CNN model, since the prediction could not be well tuned by using a small dataset in our model. Therefore, we will feed the models with a large size dataset and also optimize our CNN model to adapt for more application scenarios in the future.
