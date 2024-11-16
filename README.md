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

Add white text ("SRINILII") to the blank image using OpenCV’s putText() function, specifying font type, size, color, and thickness.
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
text = "SRIINILII"
font = cv2.FONT_HERSHEY_SIMPLEX
cv2.putText(image, text, (50, 150), font, 2, (255, 255, 255), 3)
```
![image](https://github.com/user-attachments/assets/053781ed-01b5-4d98-aad0-eea41e0527eb)
![image](https://github.com/user-attachments/assets/d886b658-0d1f-43dd-b6fb-cf22b7db6872)



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
![image](https://github.com/user-attachments/assets/cf1a7430-eb8f-4636-b636-c66090b5a8ba)


### Use Opening operation
```
opening_image = cv2.morphologyEx(image, cv2.MORPH_OPEN, kernel)
opening_image_rgb = cv2.cvtColor(opening_image, cv2.COLOR_BGR2RGB)
plt.imshow(opening_image_rgb)
plt.title("Opening Operation")
plt.axis("off")
```
![image](https://github.com/user-attachments/assets/293df1bc-1a6e-4308-8233-eeacc7bba7c6)

# Use Closing Operation
```
closing_image = cv2.morphologyEx(image, cv2.MORPH_CLOSE, kernel)
closing_image_rgb = cv2.cvtColor(closing_image, cv2.COLOR_BGR2RGB)
plt.imshow(closing_image_rgb)
plt.title("Closing Operation")
plt.axis("off")
```

![image](https://github.com/user-attachments/assets/9493e83d-bdb5-4917-aea3-cb610f703425)


## Result
Thus the Opening and Closing operation is used in the image using python and OpenCV.
