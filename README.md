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

    face_2 = face_recognition.load_image_file("sunshine.jpg")
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
                    "Atty. Sunshine Charry A. Fajarda",
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

<div align="center">

## Officials Of The Republic Of The Philippines

</div>

<div align="justify">
    The order of precedence in the Philippines is the protocol used in ranking government officials and other personages in the Philippines. Purely ceremonial in nature, it has no legal standing, and does not reflect the presidential line of succession nor the equal status of the three branches of government established in the 1987 Constitution.

## 1.) Sara Zimmerman Duterte

<div align="justify">

Sara Duterte, 43, is the incumbent mayor of Davao City. She became the city's first female mayor and the youngest to ever be elected in its history. She is the daughter of President Rodrigo Duterte who also served as mayor of the southern city for several terms before seeking the country's highest office.

Duterte is the running-mate of Ferdinand "Bongbong" Marcos Jr., a former senator who is also the son and namesake of the late ousted dictator. She entered the vice presidential race at the last hour via substitution after initially claiming that she had no interest in seeking a national post.

Her younger brother, Davao City Vice Mayor Sebastian “Baste” Duterte withdrew his bid for reelection and substituted into the Davao City mayoral race. Their brother, Paolo Duterte, has retained his candidacy for reelection as representative of the 1st District of Davao City.

Mayor Duterte is running on shifting the system of government to federalism to veer away from what she derides as "imperial Manila," a hark back to her father's own campaign rhetoric. Her last-minute substitution into a national race is also reminiscent of her father's own run.

 ![sara](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/fa80e3e6-3835-4aed-a208-786f841de453)

## 2.) Atty. Sunshine Charry A. Fajarda

<div align="justify">
Atty. Sunshine Charry Fajarda was named Education assistant secretary while former Lanao Del Sur representative Muhammad Hussein Pangandaman is the new administrator of the Authority of the freeport of Bataan, according to the list released by the Presidential Communications Office (PCO).

  ![sunshine](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/144222201/779767ad-9ec3-4161-9b18-6a382e31fc6b)

## 3.)

  ![marilette](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/84e5a1e5-b747-43cb-8cdf-3d5be903f1f6)

## 4.)

  ![mempinnolasco](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/dd45c32c-9d24-4e18-9354-84ac533115c9)

## 5.)

  ![gina](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/6483338a-7773-4a67-8871-5ec7ff57271e)
 

## Unknown Teaching Personnel from University and Senior High School
The following faces below are both from the teaching force of Batangas State University and Our Lady of Peace Academy. The group chose them since they are also inclined with the primary topic "school" as they belong to a teaching institution. 


#### 1.)
![sirlouie](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/8a8f26ab-b5e4-4f9f-a891-96bd6dcf0772)

#### 2.)
![ronnel](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/a26a52d7-46cc-4d1d-b105-d2cf5463f2e9)

#### 3.)
![mikko](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/50f44863-98a1-42c1-858b-91ef2bc5c181)

#### 4.)
![aybee](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/08a3e95a-9fef-4b38-b69b-61602458a280)

#### 5.)
![kevin](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/02836036-871d-413b-8621-6cce52936c1a)

#### 6.)
![kier](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/75a2f23d-10ea-4e0e-94f4-95be4a00bf62)

#### 7.)
![erikka](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/ead9f134-1ac7-44f3-b15e-4a458699a5e2)

#### 8.)
![finny](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/edc68ebb-c6a3-47ad-9244-3bf8cfc0855d)

#### 9.)
![aggarri](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/62955bd0-5148-4eb1-bb2a-b953495903cd)

#### 10.)
![amboy](https://github.com/itsayeee/GROUP12_FINALS_FACERECOGNITION/assets/143716528/5bd8c823-9f0c-4604-bcce-4e1f7581b54b)

## Link for the Google Colab Notebook
https://colab.research.google.com/drive/1g3t00SkJwIkilwauYpvOBfvV-PrenRUW?authuser=1#scrollTo=DqMp6O6BQpUK

## References
* https://en.wikipedia.org/wiki/Department_of_Education_(Philippines)
* https://www.deped.gov.ph/contact-us/directory/
