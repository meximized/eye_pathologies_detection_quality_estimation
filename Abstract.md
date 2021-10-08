# Eye pathologies detection quality estimation

## Abstract

There are numerous implementations of neural networks in healthcare industry nowadays. 
Some of them are aimed to speed up some basic tasks such as disease diagnosis based on the snapshot of a tissue site subject to pathological changes. 
In my particular case, the task of neural network is to mark pathological areas on a human eye fundus snapshot. 

But here come the issue with these snapshots. 
The sense of sight of patients with eye fundus pathologies does often have some imperfections, 
and such imperfections called aberrations spoil the clarity of obtained images. 
Regaining this clarity is a tough task, especially if you don't have a map of aberrations of this particular eye 
which in turn requires implementation of some expensive assays. Moreover, removing the harm of some aberrations is imposible due to the image information loss they cause. 
However, there is an easier way to overcome this issue. We can train our neural network to detect pathological areas on distorted images, 
but before that it is crucial to understand how these aberrations affect the performance of the current algorithm.

To execute this task we add some distortions to the source clear image via Fourier transform. 
To add aberrations to the image one need to perform a convolution on image and distortions. 
Certain conditions allow us to simplify the operation of convolution and multiply Fourier spectra of image and aberration (the Fourier spectrum of different Zernike polynomials)
and then apply the reverse transform on the result of the multiplication. We can change the extent of distortions applied by tuning the abberations' amplitude.

The neural network then process the source image with the array of distorted images. And here comes further processing, the subject of my [work](./README.md).
