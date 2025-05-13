### Learning the framework of a neural network 

- A neural network is something which connects explanatory variables to the final outcome (here, we have dogs and cats). <br>
- The NN is defined when the explanatory variables are connected to a 'hidden layer' of neurons, which is then connected to the outcomes <br>
- A Deep Neural Network is defined when there are multiple hidden layers <br>

![Model Diagram Overview](diagrams/model_overview.png)

Essentially, a neural network will identify the image and come up with a maximum likelihood for the image being a cat or dog, by summing up all the probabilities from each neuron and placing it on a sigmoid distribution. <br><br>
It will then produce a probability for finding whether the image is a cat or dog, giving a probability for each. <br><br>
For example, if the output gives that the image is 75% dog and 25% cat, we take the arg(ument) max ($arg max$) and essentially idenify the image to be a dog.

![Sigmoid Distribution Shape](https://storage.googleapis.com/lds-media/images/sigmoid-function-binary-classification-exampl.width-1200.png)

### Tensorflow terminology 
- The flatten layer reshapes multidimensional tensors into a single 1D vector, hence the name 'flattening'.<br>><br>
- The dense layer is a fully connected layer that learns complex patterns from the input. <br><br>
- *Flatten* is typicaly used before *Dense* layers in CNNs to prepare data 

![Flattening vs Dense](https://i.sstatic.net/wCL4l.png)

- *model.add* is used to add layers to a model when we used the **sequential** model. <br><br>

- 🤖 *keras* is a high-level neural network API <br><br>

- *relu* stands for rectified linear unit - it outputs the input directly if its positive, and zero if otherwise. This will create the sigmoid distribution that was discussed previously. <br><br>

**What does relu do?** 
🤖 Relu is an activation trigger at each neural layer. It is a popular activation function in neural networks. <br>
It is mathematically defined as: <br>
$ReLU(x) = max(0,x)$. <br>
This was mentioned previously: *outputs the input directly if its positive, and zero if otherwise* <br><br>
It is used due to non-linearity. Neural networks need non-linear actication functions to learn complex patterns. ReLU introduces non-linearity in a very simple, discrete linear form. <br><br>

- *model.compile* is once we have setup the framework of our model and want to assemble parameters for training the model. <br><br>

- With a CNN, its objective is not to maximise the success rate (optimise for accuracy), but instead tries to minimise the rate of failure. <br><br>

- *adam* is an adaptive learning rate optimising algorithm, the default optimiser. But we can also implment other ones from Keros, like stochastic gradient descent. <br><br>

- Categorical Crossentropy is a commonly usd loss function in classification problems where the target variable is categorical, if it falls into one of several possible classes. t can be broken down into several types:<br>
    - Categorical Crossentropy = use when there is more than two classes labels are one-hot encoded vectors [0, 0, 1, 0]<br>
    - Sparse Categorical Crossentropy = use when there are more than two classes and labels are integers, e.g. 2<br>
    - Binary Crossentropy = use when there are only two classes (e.g. cat and dog) and labels are 0 or 1. Works with the sigmoid output.<br>
        Formula: $\text{Loss}=-[y\dot log(\hat{y})+(1-y)\dot log(1-\hat{y})]$<br><br>

*pickle library*
``` pickle_out = open("X.pickle", "wb") ``` opens a the file X.pickle to save the data
``` pickle.dump(X, pickle_out) ``` dumps the X data into the X.pickle file
``` pickle_out.close() ``` closes the file



### Sources of learning
- https://www.youtube.com/playlist?list=PL9r1eAj4nrG0JBfOPqp_yz1w13geQMdea
