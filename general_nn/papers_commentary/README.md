### Papers [[Commentary](papers_commentary)]

#### ** Dropout ** 

1. [Dropout:  A Simple Way to Prevent Neural Networks from Overfitting](http://jmlr.org/papers/volume15/srivastava14a/srivastava14a.pdf)   

 This is (I think - it's hard to tell) the canonical paper introducing the concept of dropout in neural networks (an earlier version of the paper can be found in [arxiv](http://arxiv.org/pdf/1207.0580.pdf)). It gives great motivation for the use of dropout, and a good amount of digestible detail on the structure and implementation of a neural network using dropout. It motivates the intuition behind dropout well, and includes some nice visuals to help show what goes on in networks using dropout. 

 My main takeaways are as follows: 

* There are two main motivations for dropout: 
 * Dropout is a technique to help prevent/correct for overfitting. 
 * Dropout allows us to effectively perform model averaging by building loads of thinned networks that have learned different features. 
* It is successful for two reasons: 
 * It leads to less complex networks, which means we are less likely to overfit. 
 * It helps prevent the hidden units in our network from co-adapting, and instead leads to hidden units learning more useful features on their own (e.g. irrespective of what other hidden units are learning). If we look at the activations of the nodes in each layer of the net with and without dropout, we see that with dropout, we have fewer nodes that have high activation (suggesting that fewer nodes are learning at any given time, helping to prevent nodes from co-adapting). 
* It is implemented by randomly dropping out some subset of nodes/neurons in each layer, where we can specify the probability `p` of dropout in each layer.  

[@sallamander](https://github.com/sallamander)


#### ** Convolutional Neural Networks **

1. [ImageNet Classification with Deep Convolutional Neural Networks](http://papers.nips.cc/paper/4824-imagenet-classification-with-deep-convolutional-neural-networks.pdf)

The ImageNet Large Scale Visual Recognition Challenge (ILSVRC) has been running since 2010 and produces revolutionary insights into computer vision year after year. This 2012 paper and corresponding model architecture (AlexNet, named after the lead author, Alex Krizhevsky) ushered in the era of deep neural networks for image classification. AlexNet shattered the records set by raw vector-based methods in 2010 and 2011, and every winning method since has utilized deep learning in some fashion. 

AlexNet by the numbers:
* 5 convolutional layers & 3 fully connected layers.
* 60 million parameters & 650,000 neurons.
* 15.3% top-5 test error rate in ISLVRC; second place was at 26.2%.

Reasons for success:
* ReLU activations rather than the previous standard tanh, providing:
  * A non-saturating non-linearity that significantly enhances training speed (tanh saturates easliy).
  * An efficient method for sparsifying networks (tanh does not lead to sparse networks).
* Brightness normalization after certain ReLU layers.
* Overlapping pooling (stride=2px, poolsize=3x3), making it harder to overfit the training data.
* Dropout (only recently developed) on the first two fully connected layers, reducing overfitting, but approximately doubling the number of iterations needed to converge.

Limitations:
* Utilized a large convolutional kernel (11x11) and a long stride (4 pixels) on the first layer, significantly reducing dimensionality and effectively throwing away information. Since 2012, top CNNs tend to use small (3x3 or 5x5) kernels with a stride of 1 pixel.
* Not very "deep" by today's standards.

[@jliemansifry](https://github.com/jliemansifry)

