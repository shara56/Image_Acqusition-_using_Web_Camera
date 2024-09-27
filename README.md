# Image_Acqusition-_using_Web_Camera
## Aim
 
Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera
<br>
### Step 2:
Use cv2.imread to read the video or image
<br>
### Step 3:
Use cv2.imwrite to save the image
<br>
### Step 4:
Use cv2.imshow to show the video
<br>
### Step 5:
End the program and close the output video window by pressing 'q'.
<br>
## Program:
``` Python
### Developed By:Sharangini T K
### Register No:212222230143
```
## i) Write the frame as JPG file

```
import cv2 
cap=cv2.VideoCapture (0) 
frame_number=0 # Initialize frame number
while frame_number < 5:
    ret, frame= cap.read()
    cv2.imshow('frame', frame) 
#Save frame as JPG file
    cv2.imwrite(f"frame_{frame_number}.jpg", frame)
    frame_number += 1 
    if cv2.waitKey(1) & 0xFF == ord('q'):
     break
cap.release()
cv2.destroyAllWindows()
```

## ii) Display the video
```

import cv2
cap= cv2.VideoCapture(0)
while True: 
    ret, frame= cap.read()
    cv2.imshow('Video', frame) 
    if cv2.waitKey(1) & 0xFF== ord('q'): 
      break 
cap.release()
cv2.destroyAllWindows()
```

## iii) Display the video by resizing the window

```
import cv2

cap = cv2.VideoCapture(0)
# Create a resizable window
cv2.namedWindow('Video', cv2.WINDOW_NORMAL)

while True: 
    ret, frame = cap.read()
    if not ret:
        break
    cv2.imshow('Video', frame)
    
    # Resize the window
    cv2.resizeWindow('Video', 100, 200)
    
    if cv2.waitKey(1) & 0xFF == ord('q'): 
        break 

cap.release()
cv2.destroyAllWindows()
```


## iv) Rotate and display the video

```
import cv2
cap = cv2.VideoCapture(0)
# Define the rotation angle (in degrees)
rotation_angle = 90

while True:
    ret, frame = cap.read()
    if not ret:
        break
    # Rotate the frame
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    
    # Display the rotated frame
    cv2.imshow('Rotated Video', rotated_frame)
    
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break

cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![WhatsApp Image 2024-09-26 at 9 59 45 PM](https://github.com/user-attachments/assets/99915b77-bf22-4744-bc9b-96ffd6476c4b)


### ii) Display the video

![WhatsApp Image 2024-09-26 at 9 59 45 PM (1)](https://github.com/user-attachments/assets/2294fd01-bd49-49d1-9250-f7b81453789f)


### iii) Display the video by resizing the window


![WhatsApp Image 2024-09-26 at 9 59 46 PM](https://github.com/user-attachments/assets/c1ca4ece-0bbd-453a-86c3-afd6eca7edff)

### iv) Rotate and display the video

![WhatsApp Image 2024-09-26 at 9 59 46 PM (1)](https://github.com/user-attachments/assets/2b9304ec-44f6-4fed-82e0-4aef1c1e5155)



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
