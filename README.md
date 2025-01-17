# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:

Load the necessary packages.

### Step2:

Read the Image and convert to grayscale.

### Step3:

Use Global thresholding to segment the image.

### Step4:

Use Adaptive thresholding to segment the image.

### Step5:

Use Otsu's method to segment the image.

## Program
```


# Load the necessary packages

import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale

image=cv2.imread("moana.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("moana.jpg",0)




# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,130,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)


# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


# Use Otsu's method to segment the image 

ret,thresh_img6=cv2.threshold(image_gray,10,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU) 


# Display the results

titles=["Gray Image","Threshold Image (Binary)","Threshold Image (Binary Inverse)","Threshold Image (To Zero)"
       ,"Threshold Image (To Zero-Inverse)","Threshold Image (Truncate)","Otsu","Adaptive Threshold (Mean)","Adaptive Threshold (Gaussian)"]
images=[image_gray,thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,9):
    plt.figure(figsize=(10,10))
    plt.subplot(1,2,1)
    plt.title("Original Image")
    plt.imshow(image)
    plt.axis("off")
    plt.subplot(1,2,2)
    plt.title(titles[i])
    plt.imshow(cv2.cvtColor(images[i],cv2.COLOR_BGR2RGB))
    plt.axis("off")
    plt.show()


```
## Output

### Original Image
![Y1](https://github.com/Sharmilasha/THRESHOLDING/assets/94506182/bec11dc2-b1e7-41a4-aa54-d9bfe64d1f2a)


### Global Thresholding
![Y2](https://github.com/Sharmilasha/THRESHOLDING/assets/94506182/e021280c-78b3-476a-a6ba-4b1c9e4f802e)
![Y3](https://github.com/Sharmilasha/THRESHOLDING/assets/94506182/f4474b13-c641-44e9-846e-44a9f00a0a75)
![Q1](https://github.com/Sharmilasha/THRESHOLDING/assets/94506182/ab62a13a-e075-4920-8f2d-6bcc93d5c4dc)
![Q2](https://github.com/Sharmilasha/THRESHOLDING/assets/94506182/14c01ce9-ea9b-4605-890d-e2ae76fadc3a)
![Q4](https://github.com/Sharmilasha/THRESHOLDING/assets/94506182/ea273a46-86ae-4827-b5aa-1f67fbab8893)

### Adaptive Thresholding
![qe](https://github.com/Sharmilasha/THRESHOLDING/assets/94506182/7059afa9-3930-4443-af31-bb41482030d1)
![kw](https://github.com/Sharmilasha/THRESHOLDING/assets/94506182/834ea426-a8cd-49a0-97d1-f6a825df2f77)

### Optimum Global Thesholding using Otsu's Method
![Q5](https://github.com/Sharmilasha/THRESHOLDING/assets/94506182/2bb63cd1-2d7a-4d2c-b31f-7b7333de6a9a)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

