# Histogram-of-an-images
## Aim
To obtain a histogram for finding the frequency of pixels in an Image with pixel values ranging from 0 to 255. Also write the code using OpenCV to perform histogram equalization.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Read the gray and color image using imread()

### Step2:
Print the image using imshow().



### Step3:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### step4:
Use calcHist() function to mark the image in graph frequency for gray and color image.

### Step5:
The Histogram of gray scale image and color image is shown.


## Program:
```python
# Developed By: Rakshitha J
# Register Number: 212223240135

import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('parrot.jpg',cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title("Original Image")
plt.show()

plt.hist(img.ravel(),256,range=[0,256])
plt.title("Original Image")
plt.show()

# Name : Rakshitha J
# Reg no : 212223240135

img_eq=cv2.equalizeHist(img)

plt.hist(img_eq.ravel(),256,range=[0,256]);
plt.title('Equalized Histogram')

plt.imshow(img_eq, cmap='gray')
plt.title("Original Image")
plt.show()

# Name : Rakshitha J
# Reg no : 212223240135

img = cv2.imread('parrot.jpg',cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:,:,2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)

plt.figure(figsize=(10,12))
plt.subplot(121) ; plt.imshow(img[: , : ,::-1]); plt.title('Original Color Image')
plt.subplot(122) ; plt.imshow(img_eq[: , : ,::-1]); plt.title('Equalized Image')
plt.subplot(321) ; plt.hist(img.ravel(),256,range =[0,256]);plt.title('Original Image')
plt.subplot(322) ; plt.hist(img_eq.ravel(),256,range =[0,256]);plt.title('Histogram Equalized Image')
```
## Output:

### Original Image:

![download](https://github.com/user-attachments/assets/e81836f2-2211-4c24-8dfc-356aed85df26)

### Histogram of Original Image:

![download](https://github.com/user-attachments/assets/f44d4151-7b91-47cc-abaf-12774e55ad25)

### Histogram Equalization of Original Image:

![download](https://github.com/user-attachments/assets/cb6c85ae-6e7e-4e82-8d1a-b08bf03d33c6)

## Original Gray Image :

![download](https://github.com/user-attachments/assets/06032e40-0384-4830-9f3f-78a2cdd97357)

## Histogram Equalized Image :

![download](https://github.com/user-attachments/assets/bc1e9dc1-299d-495a-a401-7fa8360d70ac)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
