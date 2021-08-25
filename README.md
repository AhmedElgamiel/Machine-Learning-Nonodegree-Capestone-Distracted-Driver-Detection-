# Capestone Project - Distracted Driver Detection

[Machine Learning Nanodegree]

## Problem Statement
The problem that we are trying to solve is a multi-class classification problem. We are tasked to properly predict and classify driver’s behavior given the dashboard images of people doing 10 different actions, 9 of which are considered actions of distracted behavior. The 10 classes are as follows: c0: safe driving, c1: texting – right, c2: talking on the phone – right, c3: texting – left, c4: talking on the phone – left, c5: operating the radio, c6: drinking, c7: reaching behind, c8: hair and makeup, c9: talking to passenger.

## Solution steps :
A. Data Preprocessing :
   1. Images are converted into 3 channels, RGB
   2. Images are resized to 224 x 224
   3. Image labels are converted to categorical integer features/vectors
   4. The list of Images is shuffled
   5. The list of images are divided into a train set and validation set
   6. Pixel values are converted to 32-bit floats
   7. Pixel values are divided by 255 – We divide our data by 255 because it is the maximum RGB value and we want our data to be within the range of 0 and 1.

B. Implemetation
   1. Import data
   2. Create Model Architecture
      1. Built my own architecture without using any Keras Application Models.
      2. Built another model using transfer learning (VGG16 net).
   3. Train model : Used Keras fit function to train the model.
   4. Test model :
      1. Used the validation set to test the model locally. Then when I was not satisfied, I tested the model on the test dataset and I got bad results , accuracy = 16.9441%.
      2. Then , I tried transfer learning using VGG16 net , I got very good results.I removed the last three layers of the VGG16 net and added three dense layers.The first two              of them has relu activation and the third has softmax. I freezed the pre-trained layers and trained only the last 3 layers with 5 epochs , batch size 20.This lowest loss          = 0.01525, and the highest accuracy = 99.5392% .
 
 C. Refinement :
   I made some modifications to the first model , First I added another convolution layer . Second , I added another dense layer with relu activation . I also added dropout to the mode    to decrease overfitting .
![Archeticture](https://github.com/AhmedElgamiel/Machine-Learning-Nonodegree-Capestone-Distracted-Driver-Detection-/blob/main/Archeticture.PNG)
   The lowest log loss that it achieved on the whole test dataset is 0.34090, and I got accuracy = 89.7295%. The model does well but it was still not enough to beat the benchmark    result of 0.248.
   Then , I tried transfer learning using VGG16 net , I got very good results. I removed the last three layers of the VGG16 net and added three dense layers. The first two of them    has relu activation and the third has softmax. I freezed the pre-trained layers and trained only the last 3 layers with 5 epochs , batch size 20. This lowest loss = 0.01525,      and the highest accuracy = 99.5392% .
 ![Archeticture2](https://github.com/AhmedElgamiel/Machine-Learning-Nonodegree-Capestone-Distracted-Driver-Detection-/blob/main/Archeticture2.PNG)
   
 
 C. Testing and Results :
   After Refinement , here is the final results
  ![Results](https://github.com/AhmedElgamiel/Machine-Learning-Nonodegree-Capestone-Distracted-Driver-Detection-/blob/main/Results.PNG)
