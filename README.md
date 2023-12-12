# GROUP12_FINALS_FACERECOGNITION

![Group12](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/5d2b85d9-2322-40c3-b54b-4b8ffa60205b)


**_Authors: Cornejo, Ayessa Joyce C. , Agno, Christian Levi S. , Siervo, Jamaica C._**

## About

For this final requirement, the group is tasked to create a facial recognition that will identify both known and unknown faces related to the given topic. This should be aligned with the previous activity which is about school as the primary topic. In this activity, the group tends to identify the faces of the officials of the Department of Education as well as the unknown members of the school e.g teaching personnel.


![Department-of-Education-DepEd-Logo-2016](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/9bc4839c-7241-4a3e-9f9d-870b1e8404b9)

The group used the following codes for this activity to be a success:

## **Importing Images from Github and Installing Face_Recognition**

    !git clone https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION.git
    !pip install face_recognition
    %cd GROUP12_FINALS_FACERECOGNITION

## Encoding Profiles Using Known Face Images

    import face_recognition
    import numpy as np
    from google.colab.patches import cv2_imshow
    import cv2


    # Creating the encoding profiles
    face_1 = face_recognition.load_image_file("Sara Duterte.jpg")
    face_1_encoding = face_recognition.face_encodings(face_1)[0]

    face_2 = face_recognition.load_image_file("Michael Wesley Poa.jpg")
    face_2_encoding = face_recognition.face_encodings(face_2)[0]

    face_3 = face_recognition.load_image_file("marilettealmayda.jpg")
    face_3_encoding = face_recognition.face_encodings(face_3)[0]

    face_4 = face_recognition.load_image_file("mempin1.jpg")
    face_4_encoding = face_recognition.face_encodings(face_4)[0]

    face_5 = face_recognition.load_image_file("Gonong.jpg")
    face_5_encoding = face_recognition.face_encodings(face_5)[0]

    



    known_face_encodings = [
                        face_1_encoding,
                        face_2_encoding,
                        face_3_encoding,
                        face_4_encoding,
                        face_5_encoding
    ]

    known_face_names = [
                    "Sara Duterte",
                    "Atty. Michael Wesley Poa",
                    "Marilette Almayda",
                    "Nolasco Mempin",
                    "Gina O. Gonong",
    ]


## Running of Face Recognition on the officials of DepEd
        This Python script utilizes the face_recognition library and OpenCV to perform face recognition on an uploaded image. It detects faces in the image, compares their encoded data to known encodings, and displays the results. Faces are identified by drawing rectangles around them and adding their corresponding names as annotations.

        file_name = " "
        unknown_image = face_recognition.load_image_file(file_name)
        unknown_image_to_draw = cv2.imread(file_name)
    
        face_locations = face_recognition.face_locations(unknown_image)
        face_encodings = face_recognition.face_encodings(unknown_image, face_locations)
    
        for (top,right, bottom, left), face_encoding in zip(face_locations, face_encodings):
          matches = face_recognition.compare_faces(known_face_encodings, face_encoding)
    
          name = "Unknown"
    
          face_distances = face_recognition.face_distance(known_face_encodings, face_encoding)
          best_match_index = np.argmin(face_distances)
          if matches[best_match_index]:
            name = known_face_names[best_match_index]
          cv2.rectangle(unknown_image_to_draw, (left, top), (right, bottom),(0,255,0),3)
          cv2.putText(unknown_image_to_draw,name, (left, top-20), cv2.FONT_HERSHEY_SIMPLEX,1,(0,0,255),2, cv2.LINE_AA)
    
        cv2_imshow(unknown_image_to_draw)

## Vice President Sara Zimmerman Duterte as Secretary of Education in the Philippines


![sara](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/fa80e3e6-3835-4aed-a208-786f841de453)



![michael (1)](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/af40abfb-7c98-4e8e-920a-ed24c10841c9)


![marilette](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/84e5a1e5-b747-43cb-8cdf-3d5be903f1f6)


 ![mempinnolasco](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/dd45c32c-9d24-4e18-9354-84ac533115c9)


 ![gina](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/6483338a-7773-4a67-8871-5ec7ff57271e)

