# Facex
Face Recognition Attendance System
This project is an attendance system that uses face recognition to track attendance for a group of individuals. The system uses the face_recognition and OpenCV libraries to recognize faces in video footage and record attendance in a CSV file.

Requirements
To use this project, you will need to have the following installed:

Python 3.x
face_recognition library (pip install face_recognition)
OpenCV library (pip install opencv-python)
A video file or webcam to capture footage
A dataset of images to use for face recognition
Usage
Clone this repository to your local machine.

Create a dataset of images for each individual you want to track. The images should be in JPEG or PNG format and should only contain one face per image. Name each image after the person it represents, e.g. john_doe.jpg.

Place the images in a subdirectory within the dataset directory, e.g. dataset/john_doe.jpg.

Open the attendance_system.py file and modify the following lines of code to match the names and locations of your dataset:

python
Copy code
emp1_image = face_recognition.load_image_file("dataset/emp1/1.jpg")
emp1_encoding = face_recognition.face_encodings(emp1_image)[0]
emp2_image = face_recognition.load_image_file("dataset/emp2/1.jpg")
emp2_encoding = face_recognition.face_encodings(emp2_image)[0]

known_face_encoding =[emp1_encoding,emp2_encoding];

known_faces_names = ["emp1","emp2"]
Change emp1, emp2, and 1.jpg to match the names of your dataset subdirectory and images.

If you want to use your own video file, change the following line of code to the path of your video file:
python
Copy code
video_capture = cv2.VideoCapture("video.mp4")
Alternatively, if you want to use a webcam to capture footage, change the following line of code:

python
Copy code
video_capture = cv2.VideoCapture(0)
Run the attendance_system.py script by typing the following command in your terminal:
Copy code
python attendance_system.py
The script will start capturing footage and recognizing faces. If a recognized face matches a name in your dataset, the person's name will be displayed on the screen along with a "Present" message. The script will also write the person's name and the current time to a CSV file in the current directory.
Conclusion
This project provides a simple and effective way to track attendance using face recognition. With a few modifications, it can be customized to suit different needs and use cases. Feel free to experiment with the code and make it your own!
