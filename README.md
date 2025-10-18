# Edge-Linking-using-Hough-Transformm
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:

Import all the necessary modules for the program.
### Step2:

Load a image using imread() from cv2 module.
### Step3:

Convert the image to grayscale.
### Step4:

Using Canny operator from cv2,detect the edges of the image.
### Step5:

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.
## Output

### Input image
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread("C:\\Users\\admin\\OneDrive\\Desktop\\DIPT\\flwr.jpeg")  
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Input Image")
plt.axis('off')
```

<img width="774" height="541" alt="Screenshot 2025-10-18 103430" src="https://github.com/user-attachments/assets/4bff054b-4592-480b-bde2-ce8a88a3a9a4" />

### grayscale image
```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```

<img width="779" height="537" alt="Screenshot 2025-10-18 103439" src="https://github.com/user-attachments/assets/cbe46580-52d2-4b6f-a437-13d4722d044a" />


### Canny Edge detector output
```

edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')

```
<img width="772" height="541" alt="Screenshot 2025-10-18 103449" src="https://github.com/user-attachments/assets/28fcfc9d-4f9b-44fd-897a-50d70834c2fb" />


### Display the result of Hough transform

```

lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  
    cv2.line(image, (x1, y1), (x2, y2), (90, 250, 79), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title("Result of Hough Transform")
plt.axis('off')

```
<img width="791" height="540" alt="Screenshot 2025-10-18 103457" src="https://github.com/user-attachments/assets/b65f8b2b-edfa-4fc3-bec0-428f462f0a10" />

## RESULT :
Thus,The Python program to detect the lines using Hough Transform run successfully.
