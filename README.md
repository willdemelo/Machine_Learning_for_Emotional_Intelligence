# Machine_Learning_for_Emotional_Intelligencce
This is a proof-of-concept for a tool to help foster emotional intelligence and assist web-based mental health interventions, including apps, websites, hotlines, etc. It takes your photo and a caption and infers your emotional state. 

## Project Overview
Emotional intelligence is defined as the ability to understand and harness our and others' emotions, and is a key factor in positively coping with personal hardship and empathetically dealing with interpersonal conflicts. It is a skill practiced by mental health professionals and volunteer counselors alike, as simply understanding our emotional state at a given moment can be challenging. Given the US' overtaxed mental health infrastucture, promoting ways for individuals to effectively manage their emotions by themselves is of vital importance. 

I thus aimed to create a tool that could infer your emotional state based on two pieces of information - a photo of your facial expression and a short caption of what just happened in your life. This approach should come as second nature among those who use social media frequently. If people could understand what they are feeling with the help of this approach, they could adapt their thinking in more productive ways (for instance, finding ways to relax if they know that thay are angry, or looking for coping mechanisms if they know they are sad). Additionally, if this tool were implemented with an app, for example, it could then recommend resources specific to its users' emotional state.

To create this tool, I utilized two machine learning models - a multilayer perceptron (MLP) for the image data and a text classifier for the caption data - and a soft voting ensemble that combines their predictions. The MLP was trained off of various images of people making different facial expressions, and the text classifier was trained off of brief comments taken from Reddit. The model can currently predict one of seven emotions from the combined output of the two models with around 52% accuracy.

There is room for improvement for the models; given that the training datasets used for the MLP and text classifier come from unrelated sources, they are not linked by a common sentiment. I believe that this negatively hampers the model's performance, as if the image and text data shared context, they would more effectively convey emotion. In the future, webscraping could be used to take posts from social media accounts such as Instagram and Facebook, separate their contents into image and text data, and then use those datasets to train each model with. That way, the training data for each model would be linked and performance of the soft voting ensemble would likely increase.

One could also attempt to separate the neutral data from the data with emotion first, using another set of neural networks, as the model struggles the most with predicting neutral expressions and comments. 

## Resources
- **Editor Used:**  Jupyter Notebook
- **Python Version:** Python 3.11.5
### Tensorflow/Keras
  These packages are necessary for constructing and implementing my neural networks. I rely on Tensorflow and Keras' packages for all of the architecture, from the basic structure to the custom callbacks.
### Sci-Kit Learn
  Sci-Kit Learn provides two important services - a way for me to vectorize text data so that I can run it through my text classifier, and a way to split my image and text data into training and testing sets.
### Numpy/Pandas
  Numpy and Pandas are needed for Tensorflow and Keras to function, and are required for loading and formatting the datasets I use.

## Bibliography
Image data was sourced from this project:
https://www.kaggle.com/datasets/praveengovi/emotions-dataset-for-nlp

Text data was sourced from this project:
https://github.com/Valendrew/ekman-emotion-detection
