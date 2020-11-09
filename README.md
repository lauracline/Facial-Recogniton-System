# Facial-Recogniton-System
Coded a facial recognition system in Python! It can recognize anyone's face in their photo. Once a face is recognized, you can also apply digital makeup to the face (like a Snapchat filter) or find your lookalike. 

The system first employs face detection to detect and locate human faces in a photograph. The system locates faces in an image using a sliding window classifier. The classification algorithm I used to detect if a region in an image contains a face is the Histogram of Oriented Gradients (HOG). 

Then, the system uses face landmark estimation to identify key points of the face, such as the tip of the nose or center of the eye. The face landmark estimation starts with a known set of points that should appear on any face (e.g., eyebrows, nose, mouth, eyes, chin, etc.) and then it moves those points around until they match the face image. The particular landmark estimation model I'm using is a 68 point face landmark model because it looks for 68 specific points. This is also what is used to apply digital makeup on the face. I also align the faces. 

Next, I use face encodings to represent a face a set of measurements so each individual will have a unique set of measurements that can be used to recognize them and match them with the nearest doppleganger. I measured the width of each eye, the size of the cheekbones, width of the mouth, length and width of the nose, etc. Then, I compared two facial measurements to see if they match. If the measurements are almost identical, then the model assumes they are the same person. 

Lastly, using my face encoding model, I can feed the model pictures of a face and get back 128 measurements to represent that face. I used Euclidean distance to calculate the similarities and differences between two faces. I set the threshold value to 0.6. If the Euclidean distance for all 128 measurements is under the threshold value, then the model will return a match. 

I encourage you to play with it yourself using your own pictures. It's a lot of fun and feel free to use the code to make your own snapchat filter. 
