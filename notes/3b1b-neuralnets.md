# Neural Networks
[What is a Neural Network?](https://www.youtube.com/watch?v=aircAruvnKk)
  
### Notes
![img.png](img.png)  

The three different 3's are particularly different, and fire different neurons when processed. Something helps us
differentiate between things that are 3's, and something that is not.
  
![img_1.png](img_1.png)
  
It's easy for a human to do, but if you had to sit down and write a program, this would become extremely difficult quickly.
  
### Neurons - Units That Store Numerical Values
A neural network's input layer can be visualized as a 28 x 28 grid, where each neuron represents a pixel in an image. Each pixel (neuron) holds a grayscale value between 0 and 1, where 0 is black and 1 is white.
![img_2.png](img_2.png)
  
The input layer consists of 784 neurons (28 x 28 = 784). The output layer contains 10 neurons, each representing the network's confidence that the input image represents that particular digit (0-9).
![img_3.png](img_3.png)
  
Hidden layers are the intermediate layers between input and output. Their size is a hyperparameter that can be adjusted based on the problem (in this example, 16 neurons were chosen).
![img_4.png](img_4.png)
  
Information flows through the network as neurons activate other neurons in subsequent layers. The final output layer's most strongly activated neuron indicates the network's prediction.
  
While humans recognize digits by identifying specific features (like loops in 8's and 9's, or curves in 3's), neural networks learn to detect patterns in a more abstract way.
  
![img_5.png](img_5.png)
  
![img_6.png](img_6.png)
  
The layers are connected together detecting edges and patterns to form a coherent result. We have control over "knobs",
called "parameters" that allow us to find the right combination over values in the neural network. They're like knobs we
can turn to focus in on the right patterns. We'll assign a "weight" to each one of the connections between our layer and
the first layer.
  
The connections between layers are defined by weights and biases. Weights determine how strongly each neuron's activation affects neurons in the next layer, while biases adjust the threshold at which neurons activate.
  
![img_7.png](img_7.png)

For each neuron in a layer, we compute a weighted sum of all inputs from the previous layer:
![img_8.png](img_8.png)
  
This weighted sum can result in any number, but we want to normalize the neuron's output:
![img_10.png](img_10.png)

To achieve this normalization, we use an activation function (like the sigmoid function) to "squash" the values into a desired range (typically 0 to 1). The sigmoid function transforms negative inputs to values close to 0 and positive inputs to values close to 1.
  
![img_9.png](img_9.png)

The alorithm to squash these numbers to the center is called the Sigmoid function. Negative values end up closest to 0, 
very positive values end up closest to 1.

![img_11.png](img_11.png)
  
Say we didn't want to choose 0-1, we might want it to be when the sum is closest to 10. We could just add -10 to the weights
before running it through the Sigmoid function. That number is called the "bias". The weights tell you what pixel pattern
the neural network is picking up on. The bias means how high we want the weights to be before neurons start getting
activated.
  
![img_12.png](img_12.png)
  
Each layer would have some weights and biases.

![img_14.png](img_14.png)
  
Learning - finding the right weights and biases. This would impossible for a human to do by hand, so we need some way for the weights and biases to be adjusted automatically. For a good idea ofwhat matrix multiplication means, review [3b1b linear algebra](https://www.youtube.com/watch?v=fNk_zzaMoSs)
  
