# Face-Aging-Gan
This project is to create a gan to take a face and then age it to 60 years old.

1)Introduction To GANs

GANs allow us generate images created by our Neural Networks, completely removing a human out of the loop.
Generative adversarial networks (GANs) was introduced by Ian Goodfellow et al. in 2014, in his paper appropriately titled “Generative Adversarial Networks”
It was proposed as an alternative to Variational Auto Encoders (VAEs) which learn the latent spaces of images, to generate synthetic images. It aimed to create realistic artificial images that could be almost indistinguishable from real ones.

The Generator & Discriminator Networks
● The purpose of the Generator Network is to take a random image initialization and decode it into a synthetic image.
● The purpose of the Discriminator Network is take this input and predict whether this image came from a real dataset or is synthetic.

Training GANs
● Training GANs is notoriously difficult. Previously we used gradient descent to change our weights to reduce our loss.
● However, in a GANs, every weight change, changes the entire balance of our dynamic system.
● In GANs we are not seeking to minimize loss, but finding an equilibrium between our two opposing Networks.


The GAN Training Process
1. Input randomly generated noisy images into our Generator Network to generate a sample images.
2. We take some sample images from our real data and mix it with some of our generated images
3. Input these mixed images to our Discriminator who will then be trained on this mixed set and will update its weights accordingly.
4. We then make some more fake images and input it into the Discriminator but we label all as real. This is done to train the Generator. We then freeze the weights of the discriminator at this stage (Discriminator learning stops), and we use the feedback from the discriminator to now update the weights of the generator. This is how we teach both our Generator and Discriminator.

Adversarial Games
1. Adversarial games is a subfield of Artificial Intelligence where two or more agents play games opposing each other in zero sum games (their loss is my gain). Examples of zero-sum games are Tic-Tac-Toe.
2. In GANs we have two adversarial networks, the Generator and the Discriminator, where each network is being trained to win over the other. The Generator tries to make better fakes to beat the Discriminator while the Discriminator learns to get better at spotting fakes.


2)Mathematics of GANs 
● Let X be our true dataset and Z be the normal distributed noise.
● Let p(z) be data from latent space Z.
● G and D are differentiable functions of generative network and
discriminative network respectively.
● D(x) represents probability that data come from real dataset X. We
train D to maximize the probability log(D(x)) and train G to
minimize log(1 — D(G(z)).
● In short they play min max game as explained above with each
other and obtain global optimality.

 

● Above function serves as a loss function for our generative
adversarial network. Now, it is important to note that log(1 —
D(G(z)) saturates so we don’t minimize it rather we
maximize log(D(G(z))).

● In order to prove that sample generated by generator network is
exactly the same as X we need to go to deeper in mathematics
and use Kullback-Leibler divergence theorem and Jensen-
Shannon divergence.
