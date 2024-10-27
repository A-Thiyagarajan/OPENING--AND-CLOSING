# OPENING--AND-CLOSING
## Aim
To implement Opening and Closing using Python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV
## Algorithm:
### Step 1:

Import essential libraries for image processing and display, including OpenCV, NumPy, and Matplotlib.
### Step 2:

Create a blank black image with specified dimensions (300x600 pixels) and color channels using NumPy.
### Step 3:

Add white text ("Thiyagarajan") to the blank image using OpenCV’s putText() function, specifying font type, size, color, and thickness.
### Step 4:

Define a 5x5 rectangular structuring element (kernel) to use in morphological operations.
### Step 5:

Display the original image (with text) by converting it to RGB color format for proper visualization with Matplotlib.
### Step 6:

Perform an Opening operation (erosion followed by dilation) to remove small noise around the text, then display the result.
### Step 7:

Perform a Closing operation (dilation followed by erosion) to fill gaps within and around the text, followed by displaying the final output.

 
## Program:

### Import the necessary packages
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = np.zeros((300, 600, 3), dtype="uint8")

```


### Create the Text using cv2.putText
```
text = "Thiyagarajan"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)
```
![image](https://github.com/user-attachments/assets/40a860b3-e1e3-47af-a9a1-f219524ad860)


### Create the structuring element
```
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))
```

### Original image
```
image_rgb = cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
plt.imshow(image_rgb)
plt.title("Original Image")
plt.axis("off")
```
![image](https://github.com/user-attachments/assets/90076c92-8068-4d65-bc01-4ed245ab4812)


### Use Opening operation
```
opening_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
opening_image_rgb = cv2.cvtColor(opening_image, cv2.COLOR_BGR2RGB)
plt.imshow(opening_image_rgb)
plt.title("Opening Operation")
plt.axis("off")
```
![image](https://github.com/user-attachments/assets/1279bec4-8ddb-4837-bd6c-5a3a3f8e1420)


# Use Closing Operation
```
closing_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
closing_image_rgb = cv2.cvtColor(closing_image, cv2.COLOR_BGR2RGB)
plt.imshow(closing_image_rgb)
plt.title("Closing Operation")
plt.axis("off")
```
![image](https://github.com/user-attachments/assets/5a9c4624-0d91-40db-a724-bfb62725fa6e)


## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
