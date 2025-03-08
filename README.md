# Video Based Attendance System

## Overview

Attendance system can be seen as one of the most important system in any organization. Traditional system of marking attendance consumes a lot of time and at the same time, it causes problems like proxy attendance. If we want to refer the record after some days, it takes time to scan through each day’s attendance. The attendance system with video is designed so that one can quickly take attendance and is less prone to errors. Attendance system video is the system based on face detection and face recognition algorithms, through which we can detect faces of students based on the unique features identified in the face and hence mark the attendance.

## Approach

1. Finding all the faces in the picture.
2. Focusing on each face and making sure that even if a face is found in different direction, it should still be the same person.
3. Selecting unique features of the face for identification.
4. Comparing the unique features of the given face with all the faces to determine the person’s name.

## Implementation

## 01: Architecture

![Architecture](https://github.com/user-attachments/assets/b9a0e8f3-a047-4e69-a1bd-ccc0664c16ce)

## 02: Methodology

1. Image acquisition: The obtained images of students are given as an input to the system.
2. Creating dataset: Before the recognition, the dataset is created to train the system, wherein we store all the images in one folder for the ease of use. For better accuracy, more than 60 images of each student is taken.
3. 128-d facial features are computed using deep learning and stored in a proper format.
4. Face Detection and Extraction: Face detection algorithm applies to identify the human faces in that image, We can detect faces in images and the location
using HOG method.
5. Face positioning:

   ![face_positioning](https://github.com/user-attachments/assets/d3349234-70a0-49c5-9535-715fdb4e97f9)
7. Face Encoding: Extract the unique facial feature for each image. Basically whenever we get the position of the face, the 128 key facial point are extracted and these 128-d facial points are stored in data file.
8. Face matching: This is used to compute the Euclidean distance between face in image and all faces in the dataset.
    
## 03: Algorithm Used:

"HOG(Histogram Oriented Gradient) for face detection":

![Algorithm_Used](https://github.com/user-attachments/assets/399390f2-eced-4c5e-9595-1538f7b29c27)

Many factors determine the method of face recognition such as pattern, size, posture, occlusion, and lighting. To find faces in an image, we’ll start by making our image black and white because we don’t need color data to find faces. Then we’ll look at every single pixel in our image one at a time. For every single pixel, we want to look at the pixels that directly surrounding it. Our goal is to figure out how dark the current pixel is compared to the pixels directly surrounding it. Then we want to draw an arrow showing in which direction the image is getting darker. If you repeat that process for every single pixel in the image, you end up with every pixel being replaced by an arrow. These arrows are called gradients and they show the flow from light to dark across the entire image. If we analyze pixels directly, really dark images and really light images of the same person will have totally different pixel values. But by only considering the direction that brightness changes, both really dark images and really bright images will end up with the same exact representation.

1. Encode a picture using the HOG algorithm to create a simplified version of the image. Using this simplified image, find the part of the image that most looks like a generic HOG encoding of a face.
2. Figure out the pose of the face by finding the main landmarks in the face. Once after finding those landmarks, use them to warp the image so that the eyes and mouth are centered.
3. Pass the centered face image through a neural network that knows how to measure features of the face. Save those 128 measurements.
4. Looking at all the faces that have measured in the past, we see which person has the closest measurements to our face’s measurements.

"CNN( Convolutional Neural Networks)":

When it comes to Computer Vision, it’s goal is to train the machines to view and recognize the world as humans do. Convolutional Neural Network (CNNs or ConvNets), which is a special type of feed-forward network which is used mostly to analyze visual imagery. Convolutional Neural Networks are very similar to ordinary neural networks but are made up of neurons that have learnable weights and biases.

![image](https://github.com/user-attachments/assets/36fbbd4c-c04d-4a47-be08-e52d3d3ba5bd)

In our application, we are using the following libraries :
1. OpenCV, which supports a lot of algorithms related to Computer Vision and Machine Learning and not to mention it’s built in Deep Neural Network which we will be using in our application.
2. Numpy, which is a package used for scientific computing with python.
3. OS, which provides a portable way of using operating system dependent functionality.


## Results

![image](https://github.com/user-attachments/assets/7a2fe9a4-c0ee-4e57-9dd1-6f15bdeff512)

## Conclusion

Face recognition is an essential feature of Image processing owing to its excellence in many areas. The advanced face recognition technology helps in improving the performance in attendance of daily activities and analysis with reduced human intervention.
