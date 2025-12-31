Import OpenCV and download the haarcascade_frontalface_default.xml file. Place it in your project folder.

1.Load the face detector with:

face_cascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')


2.Capture video from your webcam:

webcam = cv2.VideoCapture(0)


3.In a loop, read frames, convert to grayscale, and detect faces:

gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
faces = face_cascade.detectMultiScale(gray, scaleFactor=1.5, minNeighbors=4)


4.Draw rectangles around detected faces:

for (x, y, w, h) in faces:
    cv2.rectangle(img, (x, y), (x+w, y+h), (0,255,0), 3)


5.Show the video with detected faces in real-time.

Press Escape to exit and release the webcam