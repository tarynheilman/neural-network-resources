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

#### ** Activation Units ** 

 1. ** Perceptron Units ** 

    * [Neural Networks and Deep Learning: Chapter 1](http://neuralnetworksanddeeplearning.com/chap1.html#perceptrons)

    This isn't quite a paper, but in his book Nielsen gives a clear definition of what a Perceptron unit looks like and how it works. He builds the foundation of activation units well before jumping into Sigmoid Units (see below). 

[@sallamander](https://github.com/sallamander)


 2. ** Sigmoid Units ** 

    * [Neural Networks and Deep Learning: Chapter 1](http://neuralnetworksanddeeplearning.com/chap1.html#sigmoid_neurons)

    This isn't a paper either, but Neilsen does well in explaining the jump from Perceptron units to Sigmoid units. He does a good job at motivating their use - they allow us to have our output operate on a more continuous spectrum, rather than just being a 0 or 1 (as is true when we use the Perceptron). This gives us the opportunity to build neural networks that learn more effectively.  

[@sallamander](https://github.com/sallamander)


 3. ** RelU Units ** 

    * [Rectifier Nonlinearities Improve Neural Network Acoustic Models](ai.stanford.edu/~amaas/papers/relu_hybrid_icml2013_final.pdf)


