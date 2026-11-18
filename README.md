### NAME: SURYA P <br>
### REG NO: 212224230280 <br> 
### Date: 30/10/2026

## EX. No. 3 : Record Histogram Processing

# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim:

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

- Read and display a grayscale image  
- Plot histogram of the grayscale image  
- Apply histogram equalization on grayscale image  
- Read and display a color image  
- Plot histogram of B, G, R channels  
- Convert image to HSV color space  
- Apply histogram equalization on the Value (V) channel  
- Convert the enhanced image back to BGR format  
- Display original and enhanced images with histograms  

---

## Software Used:

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm:

### Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:
Read the image `parrot.jpg` in grayscale format.

### Step 3:
Display the grayscale image and plot its histogram.

### Step 4:
Apply histogram equalization using `cv2.equalizeHist()` to enhance contrast.

### Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

### Step 6:
Read the same image in color format.

### Step 7:
Split the image into B, G, R channels and plot their histograms.

### Step 8:
Convert the image from BGR to HSV color space.

### Step 9:
Apply histogram equalization on the V (Value) channel.

### Step 10:
Merge the channels and convert the image back to BGR format.

### Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

---

## Program:

### Developed By:
**Name: Surya P**

**Register No:** 212225040133


## 1. Import the required libraries and read the grayscale image.
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('surya.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.show()
```
<img width="577" height="558" alt="image" src="https://github.com/user-attachments/assets/f6d8d253-6895-4226-b6cf-4fbf6ccad6de" />



## 2. Plot the histogram of the grayscale image.
```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
<img width="741" height="565" alt="image" src="https://github.com/user-attachments/assets/47057ca0-a4ef-4114-886d-3fcac593c32f" />


## 3. Apply histogram equalization.
```
img_eq = cv2.equalizeHist(img)
```



## 4. Display the histogram of the equalized image.
```
plt.hist(img_eq.ravel(), 256, range = [0, 256])
plt.title('Equalized Histogram')
plt.show()
```
<img width="742" height="596" alt="image" src="https://github.com/user-attachments/assets/f927ffa1-0ba8-43db-9a3c-0cd32800a39f" />

## 5. Display the equalized grayscale image.
```
plt.imshow(img_eq, cmap='gray')
plt.title('Original Image')
plt.show()
```
<img width="566" height="566" alt="image" src="https://github.com/user-attachments/assets/b40ff3ce-3ae6-48a5-946c-611b2bad657f" />

## 6. Read the image in color mode and convert to HSV.
```
img = cv2.imread('surya.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
 plt.imshow(img_eq[:,:,::-1]); plt.title('Equalized Image');plt.show()
```
<img width="657" height="566" alt="image" src="https://github.com/user-attachments/assets/47a20125-66df-46c5-87e0-c13541b975dd" />


## 7. Apply histogram equalization to the V channel.
```
plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized');plt.show()
```
<img width="767" height="561" alt="image" src="https://github.com/user-attachments/assets/3ad22dcd-e8e6-4072-9184-483580584aa7" />


## 8. Display the original and equalized color images.
```
plt.figure(figsize = (20,10))
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.show()
```
<img width="1376" height="472" alt="image" src="https://github.com/user-attachments/assets/07e48f1a-bb15-45c7-b562-e9164309fe44" />


## 9. Display the original and equalized images along with their histograms.
```
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
<img width="1372" height="460" alt="image" src="https://github.com/user-attachments/assets/11723de5-1049-454b-a5e1-ba45d2d05981" />


### Grayscale Histogram Equalization:

- Original grayscale image is displayed  
- Histogram of original grayscale image is plotted  
- Enhanced image after histogram equalization is displayed  
- Histogram of enhanced grayscale image shows improved contrast  

### Color Image Histogram Equalization:

- Original color image is displayed  
- Histogram of B, G, R channels is plotted  
- Enhanced image after HSV-based equalization is displayed  
- Histogram of enhanced image shows better intensity distribution  

---

## Result:

Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
