Image_Acqusition-_using_Web_Camera
## Name: MOHAMMAD SHHAIL
## Reg No: 212223240044

 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm

Step 1:
Import the cv2 and numpy package.

Step 2:
Read the Video frame using the cv2.VideoCapture(0)

Step 3:
Write the image using imwrite().

Step 4:
Display the frame using the imshow().

Step 5:
Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().

## Program:
 
### Developed By: MOHAMMAD SHAHIL
### Register No: 212223240044

## i) Write the frame as JPG file
```
import cv2
obj = cv2.VideoCapture(0)
while(True):
    cap,frame = obj.read()
    cv2.imshow('video.jpg',frame)
    cv2.imwrite("pic.jpg",frame)
    if cv2.waitKey(1) == ord('q'):
        break
obj.release()
```

## ii) Display the video
```
import cv2
img = cv2.VideoCapture(0)
while(True):
    imagee,frame = img.read()
    cv2.imshow('pic',frame)
    if cv2.waitKey(1) == ord('q'):
        break
img.release()
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
    cv2.imshow('PIC',smaller_frame)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```

## iv) Rotate and display the video

```
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = smaller_frame 
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    cv2.imshow('NATURE_PIC', image)
    if cv2.waitKey(1)==ord('q'):
        break
cap.release()
cv2.destroyAllWindows()







```
## Output

### i) Write the frame as JPG image

<img width="791" height="629" alt="433408900-10b9af13-aeb5-4cfa-9c26-aec4d9b4f35b" src="https://github.com/user-attachments/assets/0f825880-6432-469f-beb2-241f30cfc360" />


### ii) Display the video


<img width="795" height="629" alt="433409808-f7e80126-3cac-4ff0-843c-d78393eb958e" src="https://github.com/user-attachments/assets/376461dc-7740-4980-808f-b1868ce86053" />


### iii) Display the video by resizing the window

<img width="390" height="320" alt="433410247-03948ebe-d62d-47ed-8c7d-3da0aa5aaccc" src="https://github.com/user-attachments/assets/c4fb155f-d6d1-4806-b539-5f034b938d9b" />



### iv) Rotate and display the video

<img width="798" height="619" alt="433410649-f93034a0-6662-4cba-9857-4fa49d05bdec" src="https://github.com/user-attachments/assets/a4d6b6f2-c6ee-4dae-b7fd-0fdc4b07c0c9" />





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
