# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

## Step1:
Load the necessary packages.

# Step2:
Read the Image and convert to grayscale.

# Step3:
Use Global thresholding to segment the image.

# Step4:
Use Adaptive thresholding to segment the image.

# Step5:
Use Otsu's method to segment the image and display the results.
# Developed by : vasanth s
# reg no : 212222110052
## Program

```python
# Load the necessary packages

import numpy as np
import matplotlib.pyplot as plt
import cv2




# Read the Image and convert to grayscale

image = cv2.imread("aizen.png",1)
image = cv2.cvtColor(image,cv2.COLOR_BGR2RGB)
image_gray = cv2.imread("aizen.png",0)



# Use Global thresholding to segment the image

ret,thresh_img1=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(image_gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(image_gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(image_gray,100,255,cv2.THRESH_TRUNC)




# Use Adaptive thresholding to segment the image

thresh_img7=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img8=cv2.adaptiveThreshold(image_gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)


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
![image](https://github.com/vasanth0908/THRESHOLDING-/assets/122000018/7a479fcb-964a-41dc-9319-124f6ec307f6)


### Global Thresholding
![image](https://github.com/vasanth0908/THRESHOLDING-/assets/122000018/c8ac5b6c-99fd-4c50-8b41-308858c7b115)
![image](https://github.com/vasanth0908/THRESHOLDING-/assets/122000018/7f941008-54d8-4153-aba9-90d84696aa1c)
![image](https://github.com/vasanth0908/THRESHOLDING-/assets/122000018/257d5a81-977e-4bad-828e-bf4cde5b0213)
![image](https://github.com/vasanth0908/THRESHOLDING-/assets/122000018/3e7d5394-a77a-49e5-a15a-c6cd19b11c44)
![image](https://github.com/vasanth0908/THRESHOLDING-/assets/122000018/39238493-1e30-4710-a3af-c160e6ded5bf)


### Adaptive Thresholding
![image](https://github.com/vasanth0908/THRESHOLDING-/assets/122000018/b383d850-c123-4b93-a7a3-7d96bc8137d5)
![image](https://github.com/vasanth0908/THRESHOLDING-/assets/122000018/a9e5e03a-78d7-44e3-9e9f-14009a0c7a0a)


### Optimum Global Thesholding using Otsu's Method

![image](https://github.com/vasanth0908/THRESHOLDING-/assets/122000018/14e2ad50-37b8-483c-92fe-d220c6ad577b)

## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
