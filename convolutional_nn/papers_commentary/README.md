### Papers [[Commentary](papers_commentary)]

#### ** Must Reads ** 

 1. ** Alex Net ** 

   * [ImageNet Classification with Deep Convolutional Neural Networks](http://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)

 The ImageNet Large Scale Visual Recognition Challenge ([ILSVRC](http://image-net.org/challenges/LSVRC/)) has been running since 2010 and produces revolutionary insights into computer vision year after year. This 2012 paper and corresponding model architecture (AlexNet, named after the lead author, Alex Krizhevsky) ushered in the era of deep neural networks for image classification. AlexNet shattered the records set by raw vector-based methods in 2010 and 2011, and every winning method since has utilized deep learning in some fashion. 

 AlexNet by the numbers:
  * 5 convolutional layers & 3 fully connected layers.
  * 60 million parameters & 650,000 neurons.
  * 15.3% top-5 test error rate in ISLVRC; second place was at 26.2%.

 Reasons for success:
  * ReLU activations rather than the previous standard tanh, providing:
    * A non-saturating non-linearity that significantly enhances training speed (tanh saturates easily).
    * An efficient method for sparsifying networks (tanh does not lead to sparse networks).
  * Brightness normalization after certain ReLU layers.
  * Overlapping pooling (stride=2px, poolsize=3x3), making it harder to overfit the training data.
  * Dropout (only recently developed) on the first two fully connected layers, reducing overfitting, but approximately doubling the number of iterations needed to converge.

 Limitations:
  * Utilized a large convolutional kernel (11x11) and a long stride (4 pixels) on the first layer, significantly reducing dimensionality and effectively throwing away information. Since 2012, top CNNs tend to use small (3x3 or 5x5) kernels with a stride of 1 pixel.
  * Not very "deep" by today's standards.

 [@jliemansifry](https://github.com/jliemansifry)

