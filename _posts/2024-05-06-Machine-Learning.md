---
title: Machine Learning
description: AI Coursework - Machine Learning
author: Jan
date: 2024-05-06
categories: [2. Programming, AI]
tags: [coursework, abertay, ai, machine, learning, c#]
---

# Introduction and Background
---
For my coursework, I chose to train a facial emotion recognition model. Facial Emotion Recognition (FER) utilises a data set consisting of images categorized in different emotions. If a camera were pointed toward a person, it would determine the current emotional state this person is visually expressing (Andalibi et al, 2020).
FER is utilised in many aspects of the world and for my assignments throughout this course, I have looked for subjects that can also be related to audio. I considered that audio could be utilised in emotion detection to trigger sounds based on a person’s facial expression. My thought process was that people with extreme sight difficulties could hear how a person reacts, aiding them in conversation. After a brief search on google scholar, I discovered that emotion detection and audio has been researched in a vast majority of fields. One of which was registering the harmonics and loudness within the ear canal to determine which emotion had been triggered (Sezgin et al, 2012). Another article was based on facial emotion detection with audio for video capture (Krishna, 2013). It is important to note that although facial emotion recognition is a major step in the world of technology, however it also comes with caveats or even dangers as humanity becomes vulnerable to privacy risks (Andalibi et al, 2020).
My coursework is therefore designed to help me understand the functionality of emotion detection, to which extremes can I teach my AI to learn, and can it learn so much that it would have a negative impact on testing.
I based my programme off a tutorial on facial expression recognition using CNN (Kusawa, 2021). In this tutorial, Mr. Kusawa creates a basic neural network to train and validate the FER-2013 dataset (Sambare, n.d.). This works well in practice, however, as the test data is then later utilised to test the AI’s accuracy. This can cause false results as the AI will be aware of the test images, resulting in giving the AI a close to, if not 100% accuracy.
To bypass this, I modified the code to train on 70% of the dataset while 30% is used for validating the trained AI. Another cell is then utilised to load and test the trained AI which is completely unaware of the test dataset to get accurate results. Unlike in the tutorial, I decided to make use of Google Colab as I was having considerable issues with python packages and IDEs. I also had issues with timeouts on Google Colab and therefore had to purchase the pro package for me to fully reach my goals in testing.<br>

# Data Specification
---
As mentioned above, the FER-2013 dataset provided by Manas Sambare (n.d.) on the Kaggle platform was utilised. Although the dataset is mentioned within the tutorial, it was imperative to understand if this would meet personal justification for usage. The dataset is categorized in two folders “test” with 3589 images and “train” with 28709 images. Each folder contains 7 categories (angry, disgust, fear, happy, sad, surprise and neutral)(Sambare, n.d.). The images, although many, are very small. As I was making use of Google Colab, which can only retrieve data via Google Drive, it was therefore reasonable to stay with this set alone due to the small file sizes of the set. It also contains 6 universal facial expressions of emotion and a neutral state(Brooks et al, 2024) which ultimately is all that was needed to train the model.
In code, the training images were split into 70% to be utilised for training, and 30% utilised for validation on how accurate the model had been trained. A separate cell is used to load and test the model.<br>

# Methodology
---
To begin the application, several libraries were imported into the first cell. Keras, an open-source library designed for neural networks (Keras.io, n.d.), being at the forefront. It is built on top of Tensorflow, another open-source library designed to help with machine learning development (TensorFlow.org, n.d.).
An image data generator variable is then created to train the facial expression recognition model. 30% of the data is randomly split off to validate the trained data (Frick et al, n.d.).
The generator is then pre-processed using file paths to the FER-2013 dataset “train” folder, checks for the details of the images, categorises them to a subset of “training”, and stores them into a “generatorTrain” variable. Then, the generator is pre-processed once again, however, the subset is set to “validation” and stored within a “generatorValidate” variable. This way, the recognition will be able to validate its data against the data the AI learned (Frick et al, n.d.).
I made use of the “Sequential()” model from the Keras library. The reason being that the images are 2 dimensional and only need one input and output tensor (Keras.io, n.d.), therefore anything more convoluted seemed unnecessary. A multitude of layers are then added to define the model’s structure. First a 2-dimensional convolution kernel is added with 32 filters to set the image dimensions of the dataset (Keras.io, n.d.). Then, another 2d convolution kernel is added with 64 filters. A 2d max pooling operation (Keras.io, n.d.) is then added to downsample the input given. To finish the first third of the model and to prevent the input from “overfitting” (Keras.io, n.d.) a dropout layer is added. Another convolution kernel is added with 128 filters followed by the max pooling 2d method, followed by the dropout method. In the 3rd and final set of layers within the Sequential function, a flatten layer is called to flatten the input layer without affecting the batch size (Keras.io, n.d.). A dense layer is added to fully connect the neural network (Thakur.io, 2023). Followed by a dropout layer and another dense layer.

Lastly, the model is compiled and ready to be trained. The training was performed using mini-batches of 64 images each to reduce the computational requirements, as such, the step_per_epoch is set to 70% of the 28709 total images divided by 64 and the validation_steps to 305 of the 28709 total images divided by 64. During each training of the neural network, epoch values have been altered to see it’s accuracy on low and high epoch count.
The results are then saved to a .json file followed by the trained weights to be saved as a .h5 file.
The testing cell sets up a dictionary containing the emotions from the test folder within the dataset respectively and loads the .json and .h5 files containing the model and weights from the Google drive.
The images are then pre-processed, compiled and tested against the model. The reason the test is self-contained within its own cell is so that the test is non-aware or biased toward the model being trained avoiding false results (Mohandas, n.d.).
I initially toyed with the concept of utilising a webcam to attempt facial emotion detection on myself. However, when switching to Google Colab, I was unaware that webcam image capture is not possible as the platform is cloud based (Feekah, 2023) and finding a solution to this with the plethora of tests to be made, the idea was vetoed. The code has been left in the project to appreciate the effort.<br>

# Results and Conclusions
---
To conclude, I mentioned in my introduction that I wanted to understand the functionality of emotion detection, how much I could teach AI, and if it could learn that much that it would have a negative impact on testing.
Starting from a tutorial helped me setup the project in an instant which I find useful if a quick prototype is needed, however going in blindly did not make the tutorial of any use. I originally utilised IDEs such as Rider and Visual Studio, however, those were dismissed quickly as there were different versions clashing with another. Anaconda was also recommended, but this also fell through, and I ended up utilising Google Colab as the packets needed were already preinstalled.
Utilising Python for the first time was also a difficult hurdle to pass, however with the aid of peers and family members, I slowly grasped the concept of the language. A lot of code had to be moved around to ensure that the testing would remain non-biased to the trained model.
The performance fluctuated during the training/validation stages. This is due to the available memory on the Google Colab platform. After several timeouts on 18 epochs I made the decision to purchase the pro plan to have longer time out thresholds and better GPUs at my disposal. This dramatically reduced the training period and therefore more could be tested.

I ended up training from 10 to 100 epochs which gave me the following results in accuracy during training in comparison to testing:

![testingOne](/assets/img/AI/100epochs.png){: width="350" .w-5 .normal}
![testingtwo](/assets/img/AI/100epochs2.png){: width="350" .w-5 .normal}

I also logged the loss of both training and testing phases:

![testingthree](/assets/img/AI/loss100.png){: width="350" .w-5 .normal}
![testingfour](/assets/img/AI/loss1002.png){: width="350" .w-5 .normal}

There does not seem to be any limitation as to how much the AI could learn. I would consider that it is purely up to the limitations of the available hardware the AI is trained on.
As to if the AI does tend to overlearn, I noticed during the training stages that the AI with 100 epochs (Appendix A) would have accuracies of 90%. This got me quite excited as to see how accurate the testing would be. Interestingly enough, the AI would not reach the 60% threshold when testing and showed similar results to the Trained AI with 50 epochs (Appendix B). Therefore, I would conclude that the AI does not necessarily overlearn and perform worse, but it does seem to limit itself when reaching a certain point in training.
