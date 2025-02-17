---
title: Training a Facial Emotion Recognition AI Model
description: An introduction to Machine Learning
author: Jan
date: 2024-05-06
categories: [University Work]
tags: [coursework, abertay, ai, machine learning, c#]
---

🎮 [Check out my other projects](https://janhuss.github.io/categories/)

# Introduction

For this coursework, I trained a **Facial Emotion Recognition (FER) model** to detect **human 
emotions from images** using a dataset categorized by different facial expressions.

FER is widely used in **various fields**, from **human-computer interaction** to **emotion-based 
audio feedback**. I was particularly interested in **how well an AI can learn to detect emotions**,
whether it could **overtrain**, and how to ensure an unbiased model.

The project was inspired by a **tutorial on facial expression recognition using CNNs**, 
but I modified the approach to **train and validate the AI using separate datasets** to prevent 
false accuracy results.

# Dataset & Training Approach

The **FER-2013 dataset** from Kaggle was used, containing:

- **28,709 training images** and **3,589 test images**.
- **Seven categorized emotions**: Angry, Disgust, Fear, Happy, Sad, Surprise, and Neutral.
- **Small image sizes**, making it efficient for training in **Google Colab**.

To ensure **valid training**, I modified the dataset split to:
- **70% for training** and **30% for validation**.
- **A separate, unseen dataset for testing**, preventing the AI from memorizing results.

I originally planned to integrate **live webcam detection**, but due to **Google Colab’s** 
**cloud-based limitations**, this feature was scrapped.

# AI Model & Implementation

The model was built using **Keras and TensorFlow**, structured as a **Convolutional Neural 
Network (CNN)** with:

1. **Multiple convolution layers** to extract emotion-based facial features.
2. **Pooling layers** to reduce dimensions and improve computational efficiency.
3. **Dropout layers** to prevent overfitting.
4. **Dense layers** for final classification of emotions.

Training was conducted in **mini-batches of 64 images**, and I tested different **epoch 
values (10 to 100 epochs)** to evaluate the model’s learning ability.

# Results & Observations

- **Higher epochs didn’t guarantee better accuracy** — a model trained for **100 epochs** showed 
**90% accuracy during training** but dropped below **60% during real testing**, similar to 
the 50-epoch model.

- **Performance fluctuated** depending on **hardware limitations** in Google Colab, requiring 
an upgrade to **Colab Pro** for improved GPU performance.

- **The AI did not show signs of overlearning** but appeared to **hit a training ceiling**, 
- limiting further improvement after a certain point.

## Accuracy Results (100 Epochs vs. Testing Performance)
![testingOne](/assets/img/AI/100epochs.png){: width="390" .w-49 .normal}
![testingtwo](/assets/img/AI/100epochs2.png){: width="390" .w-49 .normal}

## Training vs. Testing Loss Graphs
![testingthree](/assets/img/AI/loss100.png){: width="390" .w-49 .normal}
![testingfour](/assets/img/AI/loss1002.png){: width="390" .w-49 .normal}

# Final Thoughts

This project gave me **valuable insight into AI training, dataset structuring, and the 
challenges of model validation**. Key takeaways:
- **Splitting datasets properly is crucial** to avoid false accuracy results.
- **More training doesn’t always mean better performance** — AI can hit a plateau.
- **Hardware constraints significantly affect deep learning model performance.**

**This was an eye-opening experience, and I look forward to further exploring AI-driven 
emotion recognition!**
