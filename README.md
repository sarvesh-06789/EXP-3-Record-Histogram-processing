# EXP-3-Record-Histogram-processing
## NAME: SHARVESHWARAN M
## REG.NO: 212224240150


# Aim

To write a Python program using OpenCV to perform histogram equalization on both grayscale and color images to enhance image contrast and brightness.

The program performs the following operations:

* Read and display a grayscale image
* Plot histogram of the grayscale image
* Apply histogram equalization on grayscale image
* Read and display a color image
* Plot histogram of B, G, R channels
* Convert image to HSV color space
* Apply histogram equalization on the Value (V) channel
* Convert the enhanced image back to BGR format
* Display original and enhanced images with histograms

# Software Used

* Anaconda – Python 3.7

* Jupyter Notebook / VS Code

* OpenCV (cv2)

* NumPy

* Matplotlib


# Algorithm
Step 1:
Import the required libraries: OpenCV, NumPy, and Matplotlib.

Step 2:
Read the image parrot.jpg in grayscale format.

Step 3:
Display the grayscale image and plot its histogram.

Step 4:
Apply histogram equalization using cv2.equalizeHist() to enhance contrast.

Step 5:
Display original grayscale image, its histogram, enhanced image, and its histogram using a 2 × 2 grid.

Step 6:
Read the same image in color format.

Step 7:
Split the image into B, G, R channels and plot their histograms.

Step 8:
Convert the image from BGR to HSV color space.

Step 9:
Apply histogram equalization on the V (Value) channel.

Step 10:
Merge the channels and convert the image back to BGR format.

Step 11:
Display original color image, histogram, enhanced image, and enhanced histogram using a 2 × 2 grid.

# Program
Developed By:
Name: Pugazhenthi S

Register No:212224240120

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
img = cv2.imread('parrot.jpg',cv2.IMREAD_GRAYSCALE)
plt.imshow(img, cmap='gray')
plt.title('original_image')
plt.show()
```
<img width="1360" height="618" alt="image" src="https://github.com/user-attachments/assets/2b374114-c793-4850-aa9d-07a36a3988f8" />

```
plt.hist(img.ravel(),256,range = [0, 256]);
plt.title('Original Image')
plt.show()
```
<img width="1347" height="581" alt="image" src="https://github.com/user-attachments/assets/3e9a0cda-9d73-442c-97d1-ea872035836b" />

```
img_eq = cv2.equalizeHist(img)
plt.hist(img_eq.ravel(), 256, range = [0, 256]); 
plt.title('Equalized Histogram')
```
<img width="1340" height="617" alt="image" src="https://github.com/user-attachments/assets/93b61b6b-a700-44c7-be02-87742403ec6b" />

```
plt.imshow(img_eq, cmap='gray')
plt.title('original image')
plt.show()
```
<img width="1322" height="538" alt="image" src="https://github.com/user-attachments/assets/3ec9b3a9-cbe2-4827-a17d-700af19364e8" />

```
img = cv2.imread('parrot.jpg', cv2.IMREAD_COLOR)
img_hsv = cv2.cvtColor(img, cv2.COLOR_BGR2HSV)
img_hsv[:,:,2] = cv2.equalizeHist(img_hsv[:, :, 2])
img_eq = cv2.cvtColor(img_hsv, cv2.COLOR_HSV2BGR)
plt.subplot(121); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(122); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
```
<img width="1365" height="432" alt="image" src="https://github.com/user-attachments/assets/be5e22f9-d363-4bc4-b37d-3e767d362efa" />

```
plt.figure(figsize = [12,10])
plt.subplot(221); plt.imshow(img[:, :, ::-1]); plt.title('Original Color Image')
plt.subplot(222); plt.imshow(img_eq[:, :, ::-1]); plt.title('Equalized Image')
plt.subplot(223); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(224); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
<img width="1160" height="943" alt="image" src="https://github.com/user-attachments/assets/cc05c35c-fa20-4061-bd49-e58990963357" />


# Result
Thus, histogram equalization is successfully performed on both grayscale and color images using OpenCV. The contrast and brightness of the images are significantly improved, enhancing visual quality and feature visibility.
