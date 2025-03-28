
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
Use cv2.VideoCapture(0) to access web camera.
### Step 2:
Use cv2.imread to read the video or image.

### Step 3:
Use cv2.imwrite to save the image.

### Step 4:
Use cv2.imshow to show the video

### Step 5:
End the program and close the output video window by pressing 'q'

## Program:
``` Python
### Developed By:MANOJ M
### Register No:212223230122

## i) Write the frame as JPG file
```
import cv2
viedoCaptureObject=cv2.VideoCapture(0)
ret,frame=viedoCaptureObject.read()
cv2.imwrite("bald_cat.jpg",frame)
viedoCaptureObject.release()
cv2.destroyAllWindows()
```


## ii) Display the video
```
import numpy as np
import cv2

cap = cv2.VideoCapture(0)
ret, frame = cap.read()
cv2.imshow('captured_frame', frame)
cv2.waitKey(10000)
cap.release()
cv2.destroyAllWindows()
```


## iii) Display the video by resizing the window
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)

ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame

cv2.imshow('',image)
cv2.waitKey(5000)  
image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)
cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video
```
import numpy as np
import cv2
cap=cv2.VideoCapture(0)

ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame

cv2.imshow('',image)
cv2.waitKey(5000) 
image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
![image](https://github.com/user-attachments/assets/7a66adfc-f035-411f-be74-92bdeffb0c5b)



### ii) Display the video
![Screenshot 2025-03-28 052543](https://github.com/user-attachments/assets/3eba1762-4eca-43d0-abf4-ed70e7598f31)



### iii) Display the video by resizing the window
![Uploading image.png…]()



### iv) Rotate and display the video
![image](https://github.com/user-attachments/assets/3c4a72b1-cb36-41b6-a8e5-b494f1f93607)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
