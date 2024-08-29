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
Use cv2.VideoCapture(0) to access web camera.
### Step 2:
Use cv2.imread to read the video or image.
### Step 3:
Use cv2.imwrite to save the image.
### Step 4:
Use cv2.imshow to show the video.
### Step 5:
End the program and close the output video window by pressing 'q'.

## Program

 Developed By: Sharangini T K
 
 Register No: 212222230143

### i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
while(True):
    ret,frame=viedoCaptureObject.read()
    cv2.imwrite("exsecond.jpg",frame)
    result=False
viedoCaptureObject.release()
cv2.destroyAllWindows()

                              or

    import cv2
videoCaptureObject = cv2.VideoCapture(0)
frame_count = 0
while(True):
    ret, frame = videoCaptureObject.read()
    cv2.imwrite(f"frame_{frame_count}.jpg", frame)
    frame_count += 1
    
    if frame_count >= 100:
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```
### ii) Display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)
while True:
    ret,frame=cap.read()
    cv2.imshow('RESULT',frame)
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
    cv2.imshow('ksp',image)
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
    cv2.imshow('ksp',image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## Output
### i) Write the frame as JPG image
![image](https://github.com/ShanmathiShanmugam/Image_Acqusition-_using_Web_Camera/assets/121243595/3cc3d1b4-8d43-47ae-8e1f-c4e2f479fe7f)

### ii) Display the video
![image](https://github.com/ShanmathiShanmugam/Image_Acqusition-_using_Web_Camera/assets/121243595/02287db7-dc73-4574-ad71-d0d51950237a)

### iii) Display the video by resizing the window
![image](https://github.com/ShanmathiShanmugam/Image_Acqusition-_using_Web_Camera/assets/121243595/697220c8-9195-452b-819d-1d0f1a44b402)

### iv) Rotate and display the video
![image](https://github.com/ShanmathiShanmugam/Image_Acqusition-_using_Web_Camera/assets/121243595/7d85b417-99bc-4d39-913d-c356aaab9746)

## Result
Thus the image is accessed from webcamera and displayed using openCV.
