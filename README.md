# Thresholding of Images
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Load the necessary packages.
<br>

### Step2:
Read the Image and convert to grayscale.
<br>

### Step3:
Use Global thresholding to segment the image.
<br>

### Step4:
Use Adaptive thresholding to segment the image.
<br>

### Step5:
Use Otsu's method to segment the image.
<br>
### Step6:
Display the results.
<br>

## Program

```python
# Load the necessary packages
import cv2
import numpy as np
import matplotlib.pyplot as plt

# Read the Image and convert to grayscale
image=cv2.imread("porsche.jpg",1)
image=cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray=cv2.imread("porsche.jpg",0)

# Use Global thresholding to segment the image
ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)

# Use Adaptive thresholding to segment the image
thresh_img7=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptive Threshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

# Use Otsu's method to segment the image 
ret,thresh_img6=cv2.threshold(image_gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)

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
![image](https://user-images.githubusercontent.com/103049243/171176976-ae04f80b-bbe3-4812-9360-cd2b0ea2d704.png)

### Global Thresholding
![image](https://user-images.githubusercontent.com/103049243/171177023-9f6f3255-17d1-4c9e-bed5-38cabf50d1cc.png)
![image](https://user-images.githubusercontent.com/103049243/171177102-2091d682-f7f6-43c9-9cf5-e1705f4e8f6e.png)
![image](https://user-images.githubusercontent.com/103049243/171177179-8545cfc5-b385-4153-b7b2-a83aae6c7777.png)
![image](https://user-images.githubusercontent.com/103049243/171177233-d6b63b3e-2452-44b0-865f-938af1645a73.png)
![image](https://user-images.githubusercontent.com/103049243/171177274-432de8de-8923-4e91-a7af-e83fdc852185.png)

### Adaptive Thresholding
![image](https://user-images.githubusercontent.com/103049243/171177328-f678a58a-412a-4f43-8e86-123d7874f370.png)
![image](https://user-images.githubusercontent.com/103049243/171177373-a1eaeb4d-e7c6-4ea7-be48-9d3d6043dff6.png)

### Optimum Global Thesholding using Otsu's Method
![image](https://user-images.githubusercontent.com/103049243/171177446-252ad7ea-247a-4237-8aa1-a3fe0791496e.png)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.

