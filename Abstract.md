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
Certain conditions allow us to simplify the operation of convolution and reduce it to the multiplication of Fourier spectra of image and aberration (the Fourier spectrum of different [Zernike polynomials](https://en.wikipedia.org/wiki/Zernike_polynomials))
and the application of the reverse transform on the result of the multiplication. We can change the extent of distortions applied by tuning the abberations' amplitude. 

#### Example of adding distortions to the source image
| source image | moderate aberrations | strong aberrations |
|--------------|----------------------|--------------------|
|![source](https://user-images.githubusercontent.com/81490574/136656334-bdf2da34-b7bf-4254-ac2f-dc5e42120e1a.png)|![Слой 0](https://user-images.githubusercontent.com/81490574/136656336-0cf48ea4-995d-4def-bf22-59570287f044.png)|![result](https://user-images.githubusercontent.com/81490574/136656340-a7d022b2-c6d2-4c89-b10b-914d13a8f59e.png)|

The neural network then process the source image and the array of distorted images by marking out pathological areas of tissue on them. Then comes the estimation of pathology detection quality, the subject of my [work](./README.md).

#### Example of neural network image processing
| source image | moderate aberrations | strong aberrations |
|--------------|----------------------|--------------------|
|![src](https://user-images.githubusercontent.com/81490574/136656475-41890823-5777-42f0-ba8f-7d9cd0751d77.png)|![1](https://user-images.githubusercontent.com/81490574/136656569-adc44d41-1703-4170-b4c8-42cddfd4ed53.png)|![2](https://user-images.githubusercontent.com/81490574/136656571-ec886538-0174-4e1c-88d7-44183a512079.png)|


