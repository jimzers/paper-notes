# travelga

image-to-image translation by transformation vector learning

past cycle consistent models assume domains are similar. but travelgan will tackle different shapes and contexts

add a third network in addition to discriminator and generator.

a siamese network that guides the generator so that each og image shares semantics with its generated version
- now you don't need the "cycle-consistency" restriant on the generators
- this is a genrators can learn more complex mappings by larger differnces

Previously, domain translation (paper written in 2019)
- unsupervised methods to match distributions of two domains with GANs
- but theres infinitely many mappings b/w the domains

non-identifiability problem: no guarentee that an individual img in one domain will share any characteristics with its representation in the other domain 


cycle-consistency: forcing generators to be each other's inverse
- does not guarentee related real-generated img pairs
- no individual image level matching

all the work recently is just regularization regularization regularization (be inverses plz im begging u) <- this

Transformation Vector Learning GAN

siamese network => produces latent space of the data

forces generator to preserve vector arithmetic b/w points in the latent space

inspired by word2vec embeddings in NLP - generator must generator two pts in target domain separated by the same transformation vector as the original domain

travelgan: train to produce semantic vector transformations

domain mapping problem:
1. transfer given img to other domain
2. make the translated img similar to the original img in some way


groundbreaking
1. eliminate need to train on cycle-consistency / coupling gnerator weights / restricting generator architecture
2. seprate network with output space that SCORES similarity between og and generated imgs. And unlike other embeddings, this one preserves vector arithmetic and there is a decoder that must decode the embedding akin to cycle consistency
3. neural networks completely parameterize - no Euclidean distances
4. Adds interpretability to the unsupervised domain transfer task

Travelgan avoids regularizations which does a few things:
- cycle-consistecy prefers easily invertible function which may not capture everything properly
- and the invertible mappings are restricted to be inverses of eac oter
- no more pixelwise MSE!! (tendency to bias towards mean images in dataset)


unsupervised domain mapping:
1. domain membership

