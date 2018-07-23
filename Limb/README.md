# Limb Motion Recognition 
-----
<br>
The second module is the limb motion recognition module:<br>
We use the database of Kaggle competition for pre-training. Since the image size is 640*480, we chose VGGNet model;<br>
Due to the deep level of VGGNet, it is difficult for our devices to train such a complex network (mainly insufficient memory), so we used Fine-tuned technology to speed up training<br>
The so-called Fine-tuned technology is to load models that others have already trained (here is using ImageNet and trained VGGNet)<br>
Freeze the previous convolutional layer in VGG without training (this is because the convolutional layer is used to extract high-order abstract features, the image components are mostly similar, so it can be loaded directly)<br>
The second is that the convolutional layer is much more computationally complex when doing the BP algorithm, and the generalized Fourier transform is used, which is very slow<br>
Therefore, freezing the convolution layer can speed up training, which is equivalent to training only the full connection layer<br>
More about Fine-tuned technology: https://kratzert.github.io/2017/02/24/finetuning-alexnet-with-tensorflow.html<br>
  <br>
  <br>
  <br>

The core technology introduction is over you can start training, and data collection sources: https: //www.kaggle.com/c/state-farm-distracted-driver-detection <br> <br>
The train directory is a catalogue for training. There are ten categories from c0 to c9, corresponding to the one we just listed. 0. Normal driving 1. Right hand playing mobile phone 2. Right hand calling and other ten kinds of behavior. A total of 22,286 images were included in this training set. <br> <br> <br> <br>
