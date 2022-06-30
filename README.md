# Generate synthetic dog images using GANs

### Aim of the project

To generate synthetic images of dogs using Generative Adversarial Networks, which are explained below.

### What are GANs?
GANs or Generative adversarial networks are used to generate synthetic images that never existed before. They train on real-world examples to create realistic fakes.

It has 2 components:
* <b>Generator:</b> Model that is used to generate synthetic images by learning from real-world examples.
* <b>Discriminator:</b> Model that is used to classify examples as real or fake.

When training begins, the generator produces fake data and the discriminator can easily identify it as fake. As training progresses, the generator learns to fool the discriminator into classifying real images as fake by generating more realistic images.

### How does it work?

#### The Discriminator

The Discriminator is a model aimed at identifying whether an image is an actual or a fake. This model functions as a classifier. Therefore, the model architecture is a deep neural network that classifies images from the generator.

The training steps are as follows:
* The data source is real data instances that are treated as positive classes and fake data instances are treated as negative classes.
* The discriminator classifies both actual data and fake data from the generator.
* The loss penalizes the discriminator for misclassifying an actual instance as fake or a fake instance as real.
* The discriminator updates its weights through backpropagation from the discriminator loss through the discriminator network.

#### The Generator

The generator is a model that takes feedback from the Discriminator and tries to improve the generated image in a way such that the Discriminator is not able to distinguish between the actual or fake image. That is, in the next pass it classifies the fake image as real.

The training steps are follows:

* Sample random noise.
* Produce generator output from sampled random noise.
* Get discriminator "Real" or "Fake" classification for generator output.
* Calculate loss from discriminator classification.
* Backpropagate through both the discriminator and generator to obtain gradients.
* Use gradients to change only the generator weights.

### Architecture

<img width="687" alt="Screen Shot 2022-06-29 at 5 30 55 PM" src="https://user-images.githubusercontent.com/29855231/176567883-d7920095-fc77-4b11-9253-d07d468d0a44.png">

* The discriminator is a CNN-based architecture that is process the incoming images through various levels of convolution operations and a Linear layer to predict a positive or negative class.
* The generator takes in a noise sampled vector, reshapes and upsamples it into a 3D matrix, and applies  a nonlinear function to produce a generated image

### Some examples
Here are some generated dog images

<img width="526" alt="Screen Shot 2022-06-29 at 5 39 08 PM" src="https://user-images.githubusercontent.com/29855231/176568572-45729e3a-5976-4d1b-bb7b-33ae8ed8d2b6.png">

### Outcomes of the project

We were able to build a working pipeline to train GANs and learn about GAN architectures.

References : 
* https://www.researchgate.net/figure/Network-architecture-generator-top-discriminator-bottom-The-GAN-is-composed-by_fig1_335341342
* https://developers.google.com/machine-learning/gan/generator
