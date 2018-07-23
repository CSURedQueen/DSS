# Face State Recognition
-----
<br>
The first module is the face state recognition module:<br>
We use the "fer2013" database for pre-training. Since the image size is 48*48, it is not convenient to adopt a CNN model with too deep level;<br>
So we built a CNN model with only 2 to 3 convolution/pooling layers<br>
In order to speed up the training, I removed Droup-out and switched to BN (Batch Normalization) to solve the problem of gradient dispersion and over-fitting.<br>
The BN method has been implemented in the CNN model, and the specific principles can be viewed as following explanation. <br>
LINK：https://morvanzhou.github.io/tutorials/machine-learning/tensorflow/5-13-A-batch-normalization/<br>

  <br><br><br>
After training (this training model is not too complicated, so the 3G version of the GTX1060 graphics card, the training speed is also very fast), the accuracy of the training set up to 99%, but only 54% in the verification set and test set Left and right precision;<br><br>
Moreover, no matter how the network structure is adjusted, even the Droup-out method can not bring further improvement in accuracy. Therefore, I speculate that it is limited to the data itself and the network complexity. This precision is already acceptable (I saw it on Kaggle). In this type of competition, top-1 is only about 70% accurate.)<br><br>
   <br>
Therefore, after comprehensive consideration, I decided to use Bagging integrated learning method to integrate a series of heterogeneous CNN networks to achieve accuracy improvement<br>
By modifying the network structure, including the number of convolution/pooling layers and Kernel size, the number of nodes in the fully connected layer, the keep_prob ratio in the droup-out, the activation function method, etc., a total of 10 small CNN models are constructed. Accuracy is between 45% and 56%<br><br><br><br><br><br>


