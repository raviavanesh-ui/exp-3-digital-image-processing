# exp-3-digital-image-processing

# Histogram Equalization Using OpenCV (Grayscale & Color Images)

---

## Aim

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

## Software Used

- Anaconda – Python 3.7  
- Jupyter Notebook / VS Code  
- OpenCV (`cv2`)  
- NumPy  
- Matplotlib  

---

## Algorithm

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

## Program

### Developed By:
**Name:** __Avanesh.R_________________________  

### Register No:
__212225240018________________________  
```
import cv2
import numpy as np
import matplotlib.pyplot as plt

img = cv2.imread('TikTok - Make Your Day.jpg', cv2.IMREAD_GRAYSCALE)

plt.imshow(img, cmap='gray')
plt.title('Original GrayScale Image')
plt.show()

plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original GrayScale Image Histogram')
plt.show()

img_eq = cv2.equalizeHist(img)

plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Equalized Histogram')
plt.show()

img = cv2.imread('TikTok - Make Your Day.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)

img_hsv[:, :, 2] = cv2.equalizeHist(img_hsv[:, :, 2])

plt.subplot(121)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(122)
plt.imshow(img_eq[:, ::-1])
plt.title('Equalized Image')

plt.show()

plt.figure(figsize=[12,10])

plt.subplot(221)
plt.imshow(img[:, :, ::-1])
plt.title('Original Color Image')

plt.subplot(222)
plt.imshow(img_eq[:, :,])
plt.title('Equalized Image')

plt.subplot(223)
plt.hist(img.ravel(), 256, range=[0,256])
plt.title('Original Histogram')

plt.subplot(224)
plt.hist(img_eq.ravel(), 256, range=[0,256])
plt.title('Histogram Equalized')

plt.show()
```
  
---

##  Output
orginal scale img

<img width="552" height="344" alt="download" src="https://github.com/user-attachments/assets/42f4c8a3-2768-4d67-80d1-9daa57c9cb67" />

orginal gray scale img
<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/dd068c78-f547-46d3-b5e9-bed6b64fada8" />

equalized histogram

<img width="570" height="434" alt="download" src="https://github.com/user-attachments/assets/8bca3cfb-8e85-46eb-a577-a4c6c8f1b967" />

original color img
<img width="552" height="191" alt="download" src="https://github.com/user-attachments/assets/e603f160-171b-4231-b5de-cadf7cc24653" />
<img width="552" height="191" alt="download" src="https://github.com/user-attachments/assets/bbff2ffc-1396-4b25-967b-8bff25631472" />

orgial color img
<img width="1013" height="778" alt="download" src="https://github.com/user-attachments/assets/5e7e4ece-e2f8-4d80-b510-aa0c99e7312a" />
<img width="1013" height="778" alt="download" src="https://github.com/user-attachments/assets/8e292133-7d2a-4ae8-aa04-7c9ac14f567a" />

orginal histogram
<img width="1013" height="778" alt="download" src="https://github.com/user-attachments/assets/c3aeebfc-7601-45da-a8d7-6421d3216ceb" />

histogram equalized
<img width="1013" height="778" alt="download" src="https://github.com/user-attachments/assets/f72c159e-272f-4a3f-96e2-de94b13f2a3d" />


## Result

Thus, histogram equalization was successfully performed on both grayscale and color images using OpenCV. The contrast of the images was enhanced, improving the overall visual quality.
