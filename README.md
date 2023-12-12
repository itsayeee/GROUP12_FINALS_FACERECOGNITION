# GROUP12_FINALS_FACERECOGNITION

**_Authors: Cornejo, Ayessa Joyce C. , Agno, Christian Levi S. , Siervo, Jamaica C._**

## About

For this final requirement, the group is tasked to create a facial recognition that will identify both known and unknown faces related to the given topic. This should be aligned with the previous activity which is about school as the primary topic. In this activity, the group tends to identify the faces of the officials of the Department of Education as well as the unknown members of the school e.g teaching personnel.

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

    face_3 = face_recognition.load_image_file("epimaco1.jpg")
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
                    "Epimaco V. Densing III",
                    "Nolasco Mempin",
                    "Gina O. Gonong",
    ]
