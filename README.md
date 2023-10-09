## Generative Adversarial Network to Generate MNIST Digits ##

*This project was done through the guidance of an online instructor @LazyProgrammer*

### Introduction: ###
Generative Adversarial Network is a type of deep learning model that is generally used to generate realistic images. It is based on two neural networks- Generator and
Discriminator. They improve each other in tandem. The generator tries to create images that look more and more realistic so as to fool the discriminator while the discriminator becomes better and better at discriminating between real and fake images.

## Dataset ##
The MNIST Dataset is used in this project. It is loaded from the tensorflow datasets.

## Generator ##
* Generator Neural Network takes noise as input and it performs its key role of converting this noise into realistic images. This transformation process is achieved through the layers in the Artificial Neural Network. As the generator learns during training it effectively transforms the noise into a latent representation. The latent space is like an imaginary space that represents a smooth transition between images and encodes meaningful variations. This latent representation becomes more structured and meaningful over time.
* An intuitive concept would be to understand the loss function for the generator. Since if we can come up with a loss function then we can simply apply gradient descent algorithms to find the parameters. So in order to train the generator we can make a combined model that combines the generator and discriminator. The input of such a model would be noise (which would be converted by the generator into images) and the output would be the predictions made by the discriminator. In order to ensure that only the generator is trained we need to freeze the weights of the discriminator and provide output all equal to ones (where we have assumed that the discriminator sees 1s as real images and 0s as fake images). Rendering the output as an array of ones would make the generator improvise its strategy to generate more realistic images in order to minimize the loss. In this way, the output of this combined model has become binary and we can compile it in a similar way as we do it for binary classification problems.

## Discriminator ##
The main role of the Discriminator Neural Network is to discriminate between real images and fake images. It is trained with both real and fake images and with time it becomes better and better at discriminating between real and fake images. The model is therefore compiled in the same way as we do it for binary classification.

## Loss of Generator & Discriminator ##
If we look at the plot which shows the loss of both the Generator and Discriminator over training then we can notice that the loss of both seems similar and neither of the losses goes down at the cost of the other. The reason behind this is that both the Generator and Discriminator improve each other. 
