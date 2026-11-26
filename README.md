# Opening and Closing Operations Using OpenCV

## Aim

To write a Python program using OpenCV to perform morphological Opening and Closing operations on an image.

The program performs the following operations:

- Morphological Opening
- Morphological Closing

## Software Used

- Anaconda – Python 3.7
- Jupyter Notebook / VS Code
- OpenCV (cv2)
- NumPy
- Matplotlib

## Algorithm

### Step 1:

Import the required libraries: OpenCV, NumPy, and Matplotlib.

### Step 2:

Create or load an input image containing foreground objects.

### Step 3:

Display the original image.

### Step 4:

Create a structuring element (kernel) of suitable size.

### Step 5: Opening Operation

- Apply the Opening operation using the structuring element.
- Opening consists of Erosion followed by Dilation.
- Remove small foreground noises while preserving the shape of larger objects.
- Display the opened image.

### Step 6: Closing Operation

- Apply the Closing operation using the structuring element.
- Closing consists of Dilation followed by Erosion.
- Fill small holes and gaps within foreground objects.
- Display the closed image.

### Step 7:

Compare the original, opened, and closed images.

## Program

## Developed By

**Name:** MAHEMA A

**Register No:** 212225230164

```


import cv2
import numpy as np
import matplotlib.pyplot as plt

# Step 1: Create a blank image
img = np.zeros((300, 500), dtype=np.uint8)

# Step 2: Draw white foreground objects
cv2.rectangle(img, (100, 70), (300, 220), 255, -1)

# Add small foreground noise
cv2.circle(img, (50, 50), 3, 255, -1)
cv2.circle(img, (350, 100), 3, 255, -1)
cv2.circle(img, (400, 200), 3, 255, -1)

# Add small holes inside the object
cv2.circle(img, (150, 120), 5, 0, -1)
cv2.circle(img, (250, 170), 5, 0, -1)

# Step 3: Display original image
plt.figure(figsize=(6, 4))
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.axis('off')
plt.show()

# Step 4: Create structuring element
kernel = np.ones((5, 5), np.uint8)

# Step 5: Perform Opening
opening = cv2.morphologyEx(img, cv2.MORPH_OPEN, kernel)

# Step 6: Perform Closing
closing = cv2.morphologyEx(img, cv2.MORPH_CLOSE, kernel)

# Step 7: Display results
plt.figure(figsize=(12, 4))

plt.subplot(1, 3, 1)
plt.imshow(img, cmap='gray')
plt.title('Original Image')
plt.axis('off')

plt.subplot(1, 3, 2)
plt.imshow(opening, cmap='gray')
plt.title('Opening Operation')
plt.axis('off')

plt.subplot(1, 3, 3)
plt.imshow(closing, cmap='gray')
plt.title('Closing Operation')
plt.axis('off')

plt.tight_layout()
plt.show()

```

## Output

### Original Image

- The input image is displayed.
- The image serves as the source for morphological processing.
 <img width="466" height="308" alt="image" src="https://github.com/user-attachments/assets/f06b5a9e-b119-4e09-aa55-f1e2874ccc2d" />


### Opening Operation

- Original image is displayed.
- Opened image is displayed.
- Small foreground noise is removed.
- Thin protrusions and isolated pixels are eliminated.
- Object boundaries become smoother.
<img width="455" height="323" alt="image" src="https://github.com/user-attachments/assets/cd93fd4e-6bd8-4308-8d10-46517cbd94c9" />


### Closing Operation

- Original image is displayed.
- Closed image is displayed.
- Small holes and gaps inside objects are filled.
- Broken regions are connected.
- Object boundaries become more continuous.
<img width="457" height="303" alt="image" src="https://github.com/user-attachments/assets/37b9968d-ce63-4a7a-9969-77fac3530870" />

## Applications

### Opening

- Noise removal in binary images.
- Separation of connected objects.
- Preprocessing for object detection.

### Closing

- Filling small holes in objects.
- Connecting nearby components.
- Enhancing segmented regions.

## Advantages

### Opening

- Removes unwanted foreground noise.
- Preserves major object structures.
- Improves segmentation quality.

### Closing

- Restores object continuity.
- Eliminates small background gaps.
- Improves object representation.

## Result

Thus, the morphological operations **Opening** and **Closing** are successfully implemented using OpenCV. 
