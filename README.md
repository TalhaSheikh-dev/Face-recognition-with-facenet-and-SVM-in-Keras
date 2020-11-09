# Face-recognition-with-facenet-and-SVM-in-Keras
A script for face recognition using the pretrained model of facenet and a SVM as its classifier. The script is in python using keras framework for models


Here is the script for a face recognition app. We will be using MTCNN, face_net and
SVM for making this app work. THe dataset we have used is LFW(Labeled Faces in the Wild).
We will step wise go through how the app works.

# Requirements
- mtcnn
- keras
- sklearn

# Downloads
- LFW dataset is available here http://vis-www.cs.umass.edu/lfw/ and if you want to download with the direct link http://vis-www.cs.umass.edu/lfw/lfw.tgz
  Extract the LFW dataset in the lfw folder 
- Pretrained model for keras .................
- I have trained my model on first 100 people and have placed its .npz file in the above given link. If you want to train the model on your custom dataset or full LFW dataset
you can and I will explain below how.

# How does it works/Instalation 
face_recogntion.py does the face detection and extraction as mentioned above.

After this we provide the dataset to facenet model to extract feature vector for all
the faces. We have the feature vector and the names which we save in .npz as well to
later use.

feature_extraction.py is used to to do extract the face feature vectors and saving them

Now we are done with all the initials and are ready to recognize the faces.

face_recognition.py will query the image and will provide the results of recognition.
First we load the query image and extract the face out of it using MTCNN. After that
we provide it to the face_net model to predict a feature vector for the face.
We load the previously saved embeddings of our dataset now. We get feature vectors and 
names out of it. Using this data we train an SVM. After the training is done, we use
the query feature vector to get the prediction from the SVM, which is a name. 

**If you have downloaded the .npz file you only have to run face_recognition file and it will work but remember they are only for first 100 people**

# Changes to adapt your requirement
You can use other technique at place of SVM such as KNNS which can give better results.
Moreover skewing of faces and pre processing the images might increase the accuracy as well.
We can slightly modify this to turn this in to an online face recognition

# Results
 Input image Aaron_Sorkin_0001
 
 Output 
 ![](https://github.com/TalhaSheikh-dev/Face-recognition-with-facenet-and-SVM-in-Keras/blob/main/images/predicted.PNG)
