# Generate synthetic dog images using GANs

### What are GANs?
GANs or Generative adversarial networks are used to generate synthetic images that never existed before. They train on real world examples to create realistic fakes.

It has 2 components:
* <b>Generator:</b> Model that is used to generate synthetic images by learning from the real world examples.
* <b>Discriminator:</b> Model that is used to classify examples as real or fake.

When training begins, the generator produces fake data and the discriminator can easily identify it as fake. As training progresses, the generator learns to fool the discriminator into classifying real images as fake by generating more realistic images.

### How does it work?

#### The Discriminator

The discriminator in a GAN is a classifier. It tries to distinguish real data from the fake data created by the generator. It could use any architecture appropriate to the type of data it's classifying.

The discriminator's training data comes from two sources:

Real data instances, such as real pictures of people. The discriminator uses these instances as positive examples during training.
Fake data instances created by the generator. The discriminator uses these instances as negative examples during training.

During discriminator training:

* The discriminator classifies both real data and fake data from the generator.
* The discriminator loss penalizes the discriminator for misclassifying a real instance as fake or a fake instance as real.
* The discriminator updates its weights through backpropagation from the discriminator loss through the discriminator network.

#### The Generator

The generator part of a GAN learns to create fake data by incorporating feedback from the discriminator. It learns to make the discriminator classify its output as real.

The portion of the GAN that trains the generator includes:

* random input
* generator network, which transforms the random input into a data instance
* discriminator network, which classifies the generated data
* discriminator output
* generator loss, which penalizes the generator for failing to fool the discriminator


### Some examples

