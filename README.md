# Face Recognition by Eigenface
## Matlab Fast Prototyping
A face recognition system using Eigenface algorithm. 

Data: a set of  32x32 8 bit facial images.
• ALL = FA+FB (for Training Set) <br>
• FB: 23 facial images (for Testing Set)<br>

The code contains 3 components:<br>
•  Image I/O + visualization<br>
•  PCA for learning<br>
•  Recognition by nearest neighbor classification<br>

We first read all the training images in the “ALL” file then convert each 32*32 image matrix into a 32*32*1 image vector, 
which is done by the flatten function in the file. Next, we find the mean face and subtract the mean face from every image vector.
All these different face vectors will be stacked in matrix “AfterSub”. We proceed to calculate the covariance matrix of the above 
matrix then find both eigenvectors and eigenvalues of the covariance matrix. Then eigenface, which is the basis for the entire 
training dataset, will be formed. To recognize the test images, we calculate the weights of the test image and compare it with
the weights of all the images in the training dataset, result will be the one with the least error (i.e., Euclidean distance in
this case). One problem is that test images are part of training images. Our test error will be overly optimistic. That means if 
we have a different test set, the error rate will be much higher compared to the one we have. One way to increase the chances of 
successfully recognizing the images is to get images of people from different angles like side face, back, or even tilted.

![alt text](https://github.com/LinsiLin/Face-Recognition/blob/main/result.png)


Reference: M. Turk, A. Pentland, Eigenfaces for Recognition, Journal of Cognitive Neuroscience, 3(1): 71-86 (1991)

