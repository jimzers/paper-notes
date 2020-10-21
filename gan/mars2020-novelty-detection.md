# Comparison of novelty detection methods for multispectral images in rove-based planetary exploration missions



### First pass

significance:

there's a lotta data. what's interesting to look at for **science**?

4 novelty detection methods

1. Reed Xiaoli (RX) detectors
2. PCA
3. autoencoders
4. GANs



Pixel-wise RX, autoencoders trained with structural similarity loss (SSIM) can detect morphological novelties

PCA, GANs, mse autoencoders good for detecting spectral novelties

Autoencoders provide **explanatory visualizations** to understand model detections - GANs are limited in this power



Novelty detection - identify patterns in data that hawve not been previously observed - different from data distribution



The science team uses rover data to figure out which observations to make on the next Mars day in an endless cycle. But the limitations are that you only have so much time to actually make this decision (time of available communication is limited each day)

< 12 hours 

NASA mars 2020 may have < 5 hours per day to review data and find targets of interest for follow up analysis



Typically approach to novelty detectin: construct model based on typical non-novel training examples and identify novel exmaples as poorly explained by the models

Field: prioritizing imgs with novel geology in Mastcam images

SSIM gets applied to autoencoder loss, good for morphological differences (structural)

pixel spectrum representations for RX is pretty good

autoencoders are good for explanatory visualizations



