# Image_Acqusition-_using_Web_Camera
## Aim
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import necessary libraries (cv2).
### Step 2:
Open the camera using cv2.VideoCapture(0).
### Step 3:
Enter a loop to continuously capture frames from the camera.
### Step 4:
Resize each frame, create a blank image, divide it into quadrants, and assign resized frames accordingly. Rotate specific frames if needed.
### Step 5:
Display processed frames on the screen using cv2.imshow(), and continuously check for a termination signal (e.g., pressing 'q' key) to break out of the loop.

## Program:
### Developed By: Nithishkumar P
### Register No: 212221230070
## i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("image.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('Video Capture',frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=smaller_frame
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=smaller_frame
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    width=int(cap.get(3))
    height=int(cap.get(4))
    image=np.zeros(frame.shape,np.uint8)
    smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
    image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2]=smaller_frame
    image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:]=smaller_frame
    cv2.imshow('Video Capture',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output
### i) Write the frame as JPG image
![image](https://github.com/user-attachments/assets/f7bf2553-85df-4990-89f9-4c201327c8df)
### ii) Display the video
![image](https://github.com/user-attachments/assets/92e82f9d-1e78-4a27-89a1-903e32c7be80)
### iii) Display the video by resizing the window
![image](https://github.com/user-attachments/assets/583a5aaf-2171-4d21-a302-62ebcb3b3d83)
### iv) Rotate and display the video
![image](https://github.com/user-attachments/assets/1fdc0f80-9d81-43ce-b59f-f27b31af3b10)

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
