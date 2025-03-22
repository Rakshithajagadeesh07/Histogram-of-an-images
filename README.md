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
from matplotlib import pyplot as plt

gray_image = cv2.imread('car.jpg', cv2.IMREAD_GRAYSCALE)

plt.title("Grayscale Image")
plt.imshow(gray_image, cmap='gray')
plt.axis('off')

print("Name : Rakshitha J \n Register Number : 212223240135")

plt.title("Histogram of Grayscale Image")
plt.hist(gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)
plt.tight_layout()
plt.show()

equalized_gray_image = cv2.equalizeHist(gray_image)

plt.title("Histogram of Equalized Grayscale Image")
plt.hist(equalized_gray_image.ravel(), bins=256, color='black', alpha=0.6)
plt.xlim(0, 255)

plt.title("Enhanced Grayscale Image")
plt.imshow(equalized_gray_image, cmap='gray')
plt.axis('off')

import cv2
import numpy as np
import matplotlib.pyplot as plt

color_image = cv2.imread('cat.jpg')

plt.title("Input Color Image")
plt.imshow(cv2.cvtColor(color_image, cv2.COLOR_BGR2RGB))
plt.axis('off')

hist_b = cv2.calcHist([color_image], [0], None, [256], [0, 256])
hist_g = cv2.calcHist([color_image], [1], None, [256], [0, 256])
hist_r = cv2.calcHist([color_image], [2], None, [256], [0, 256])

print("Name : Rakshitha J \n Register Number : 212223240135")


plt.title("Histogram of Input Color Image")
plt.plot(hist_b, color='blue', label='Blue channel')
plt.plot(hist_g, color='green', label='Green channel')
plt.plot(hist_r, color='red', label='Red channel')
plt.show()

blue_channel_eq = cv2.equalizeHist(color_image[:, :, 0])
green_channel_eq = cv2.equalizeHist(color_image[:, :, 1])
red_channel_eq = cv2.equalizeHist(color_image[:, :, 2])

equalized_color_image = cv2.merge([blue_channel_eq, green_channel_eq, red_channel_eq])

plt.title("Equalized Image")
plt.imshow(equalized_color_image[:,:,::-1])
plt.axis('off')

```
## Output:
### Input Grayscale Image and Color Image

![Screenshot 2025-03-22 184435](https://github.com/user-attachments/assets/b69ed252-f9ec-467c-bc34-cc77c82a8b7d)

![Screenshot 2025-03-22 184455](https://github.com/user-attachments/assets/b2712f18-f2ef-4426-ae50-22f454a22cee)


### Histogram of Grayscale Image and any channel of Color Image

![Screenshot 2025-03-22 184514](https://github.com/user-attachments/assets/3180fada-7204-44c7-84fe-58747acffe55)

![Screenshot 2025-03-22 184529](https://github.com/user-attachments/assets/5f85dbba-f474-4456-91af-4f3b0df56804)


### Histogram Equalization of Grayscale Image.

![Screenshot 2025-03-22 184601](https://github.com/user-attachments/assets/82ad60df-c792-4b86-ba20-8a6f9c2e46c1)

## Result: 
Thus the histogram for finding the frequency of pixels in an image with pixel values ranging from 0 to 255 is obtained. Also,histogram equalization is done for the gray scale image using OpenCV.
