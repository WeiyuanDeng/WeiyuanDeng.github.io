---
layout: project
title: Music Instrument Classifier
date: March 16, 2017
image: /public/images/music.JPG
---

## Overview
This is a simple classifier that is able to detect single-note sounds of various musical instruments.
Currently supported types are cello, clarinet, flute, violin and piano. The audios are supposed to be single-note sounds within the 4th octave.
Created by Ivy Zheng, Weiyuan Deng and Yuchen Rao from Northwestern University.

### Dataset
The dataset used to train this classifier was collected from [London Philharmonic Orchestra Dataset](http://www.philharmonia.co.uk/explore/sound_samples). Each audio file records one note from one of the five instruments, and has a length from 0.25 seconds to 6 seconds. In total, over 600 audio pieces were used to train the classifier, and the distribution of each class was roughly the same.

### Dependencies
Python 2.7

NumPy

Scikit-Learn (sklearn)

Librosa

glob

### Implementation

#### Preprocessing
The music pieces have their leading and ending silence trimmed. The threshold of trimming is 0.001 - if the intensity of the sound in the frame is below 0.1% of the highest sound intensity in the audio file, then the frame is trimmed out.

#### Feature Extraction
The Mel Frequency Cepstral Coefficents (MFCCs) of each music piece was extracted using Librosa. For each audio file, its MFCCs are averaged to produce the final, length-20 feature vector.

#### Classification
An SVM classifier is trained from the feature vectors to determine the instrument it belongs to. The SVM classifier worked in a one-vs-rest fashion, in which it trained 5 classifiers for each intrument class against all audios that are not in that class. The kernel of the SVM classifiers is linear.

### Performance

#### Accuracy
With the given dataset and under 10-fold cross-validation, we achived a 95% accuracy on the instrument label prediction.

#### Time Efficiency
The most time-consuming part of the system is the MFCC feature extraction. However, it still needs less than a second to process a one-second audio, which makes it feasible to do real-time instrument detection.

#### Try it Out
In addition to the code for training, this [repository](https://github.com/IvyZX/music-instrument-classifier ) also includes a pre-trained model that you can play with. Try to run the following code in your terminal:

python demo.py

After that, type in the audio file path that you want to classify. It will output the musical instrument that it recognized in the audio.
