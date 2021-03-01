# Face_recog_with_siameese_network(also known as one shot recognition)
Face recognition algorithm using vggface2 pretrained weights and InceptionResnetV1(imported from facenet-pytorch)

The MTCNN computes the location of a face(it can also compute mulitple faces in a picture) and defines it with a bounding box, along with the probability of it being a face.
It is the form of a tensor. We pass this tensor to InceptionResnetV1 which computes embeddings for the face.
We compare two pics(train pic and test pic) by calculation their squared difference averages and comparing it with a hyperparameter alpha.

I chose the value of alpha by manual testing.
It failed to recognize me when i was bald vs the picture where i have lots of hair.
It also failed on a test case where it gave a false positive to my identical twin's picture.
