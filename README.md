# Implementation-of-Erosion-and-Dilation
## Aim
To implement Erosion and Dilation using Python and OpenCV.
## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step1:
Apply the dilation operation on the image using cv2.dilate() with the same structuring element. Dilation will increase the size of the white regions (text) in the image, effectively reversing the effect of erosion

### Step2:
Initialize a blank image (100 pixels high and 400 pixels wide) using NumPy. The image should be a single-channel (grayscale) array filled with zeros (black).

### Step3:
Use OpenCV's cv2.putText() function to overlay the text "HYCINTH" on the blank image. Define the font style, position, font scale, color, and thickness for rendering the text.

### Step4:
Specify the size of the structuring element (e.g., 5x5 pixels) and create a rectangular structuring element using cv2.getStructuringElement(). This element will be used for the morphological operations.

### Step5:
Apply the erosion operation on the image using cv2.erode() with the defined structuring element. Erosion will reduce the size of the white regions (text) in the image.

```
DEVELOPED BY : HARINI M D
REGISTER NO: 212222230043
```
## Program:
# Import the necessary packages
``` Python
import cv2
import matplotlib.pyplot as plt

# Create a blank image (100 pixels high and 400 pixels wide)
img = np.zeros((100, 400), dtype='uint8')
```
# Create the Text using cv2.putText
```
# Put some text on the image for demonstration
cv2.putText(img, 'HARINI', (60, 70), cv2.FONT_HERSHEY_SIMPLEX, 2, (255), 5)
```


# Create the structuring element
```
# Create a rectangular structuring element
kernel_size = (5, 5)  # Width and height of the kernel
structuring_element = cv2.getStructuringElement(cv2.MORPH_RECT, kernel_size)

# Perform Erosion
eroded_image = cv2.erode(img, structuring_element, iterations=1)

# Perform Dilation
dilated_image = cv2.dilate(img, structuring_element, iterations=1)

# Display the original, eroded, and dilated images
plt.figure(figsize=(15, 5))
```
# Original Image
```
# Original Image

plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.axis('off')

plt.show()
```
![Screenshot 2024-11-16 205632](https://github.com/user-attachments/assets/0684005c-e62c-4009-81db-8f8ebb72a3ea)


# Erode the image
```
plt.figure(figsize=(15, 5))
# Eroded Image
plt.imshow(eroded_image, cmap='gray')
plt.title('Eroded Image')
plt.axis('off')
```
![Screenshot 2024-11-16 205657](https://github.com/user-attachments/assets/1d53b765-438e-4a97-b6ec-fda30376ea20)



# Dilate the image
```
plt.figure(figsize=(15, 5))
# Dilated Image
plt.imshow(dilated_image, cmap='gray')
plt.title('Dilated Image')
plt.axis('off')
```
![Screenshot 2024-11-16 205724](https://github.com/user-attachments/assets/e8e74cdc-0ebd-4155-8d83-ba81f10db70b)


## Result
Thus the generated text image is eroded and dilated using python and OpenCV.
