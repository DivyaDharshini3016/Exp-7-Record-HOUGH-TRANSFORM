# Exp-7-Record-HOUGH-TRANSFORM
## Lane Detection
### Aim
To implement a basic lane detection pipeline using OpenCV by completing missing code segments at specified locations.

### Learning Objective

Understand each stage of image processing
Learn how to build a complete computer vision pipeline
Practice writing code in guided sections

Important Instruction: 👉 Write code ONLY in places marked as # Your Code Here 👉 Do NOT modify any other part of the code

### Software Used

Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)
NumPy
Matplotlib

### Algorithm & Explanation

#### Step 1: Import Libraries
import cv2
import numpy as np
import matplotlib.pyplot as plt

#### Step2:
Load a image using imread() from cv2 module.

#### Step3:
Convert the image to grayscale.

#### Step4:
Using Canny operator from cv2,detect the edges of the image.

#### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

### Developed By
#### Name: Divya Dharshini S
#### Register No: 212224240039

### Program:

```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('image.JPG')
# Step 3: Convert the image to grayscale
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
# Input image and grayscale image
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Convert image to RGB for displaying
plt.title("Input Image")
plt.axis('off')
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
# Step 4: Using Canny operator from cv2, detect the edges of the image
edges = cv2.Canny(gray_image, 50, 150)
# Canny Edge Detector output
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)# Draw green lines with thickness of 2
# Display the result of Hough Transform (Image with lines)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  # Image with lines drawn
plt.title("Result of Hough Transform")
plt.axis('off')
```
### Expected Output

#### Original image

<img width="775" height="547" alt="image" src="https://github.com/user-attachments/assets/b27a7b13-6d60-46dc-8d94-46e82efa505e" />

#### Grayscale image

<img width="821" height="545" alt="image" src="https://github.com/user-attachments/assets/b02e7e5b-8fcd-47ca-8fbb-95b3743d3450" />

#### Canny Edge Detector image

<img width="776" height="543" alt="image" src="https://github.com/user-attachments/assets/4a3551d9-f809-4f18-aa0a-d372a768adf3" />

#### Result of Hough Transform image

<img width="822" height="535" alt="image" src="https://github.com/user-attachments/assets/18b84dcc-f3ad-4ac4-a3ce-c524b6e72d73" />

#### Result
Thus, the lane detection pipeline is successfully implemented by completing the missing code sections. The system detects and highlights lane lines effectively.

