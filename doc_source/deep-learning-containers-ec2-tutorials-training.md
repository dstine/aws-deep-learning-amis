# Training<a name="deep-learning-containers-ec2-tutorials-training"></a>

This section will guide you on how to run training on Deep Learning Containers for EC2 using MXNet and TensorFlow\.

**Topics**
+ [TensorFlow Training](#deep-learning-containers-ec2-tutorials-training-tf)
+ [Training with MXNet](#deep-learning-containers-ec2-tutorials-training-mxnet)

For a complete list of AWS Deep Learning Containers, refer to [Deep Learning Containers Images](deep-learning-containers-images.md)\. 

## TensorFlow Training<a name="deep-learning-containers-ec2-tutorials-training-tf"></a>

 We can run containers with the following commands\. Please note that you must use 'nvidia\-docker' for GPU images\. 
+ For CPU:

  ```
  docker run -it <cpu training container>
  ```
+ For GPU:

  ```
  nvidia-docker run -it <gpu training container>
  ```

 The previous command runs the container in interactive mode and provides a shell prompt inside the container\. You can then run the following to import TensorFlow: 
+ 

  ```
  $ python
  ```
+ 

  ```
  >> import tensorflow
  ```

 Press CTRL \+D to return to the bash prompt\. Run the following to begin training: 
+ 

  ```
  git clone https://github.com/fchollet/keras.git
  ```
+ 

  ```
  cd keras
  ```
+ 

  ```
  python examples/mnist_cnn.py
  ```

You will see that training has started\.

## Training with MXNet<a name="deep-learning-containers-ec2-tutorials-training-mxnet"></a>

To begin training with MXNet, first run the following command to run the container:
+ For CPU:

  ```
  docker run -it <cpu training container>
  ```
+ For GPU:

  ```
  nvidia-docker run -it <gpu training container>
  ```

In the terminal of the container, run the following to begin training:
+ For CPU:

  ```
  git clone -b v1.4.x https://github.com/apache/incubator-mxnet.git
  python incubator-mxnet/example/image-classification/train_mnist.py
  ```
+ For GPU:

  ```
  git clone -b v1.4.x https://github.com/apache/incubator-mxnet.git
  python incubator-mxnet/example/image-classification/train_mnist.py --gpus 0
  ```