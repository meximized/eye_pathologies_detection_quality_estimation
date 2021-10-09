# Eye pathologies detection quality estimation

You can look through a brief background of this work [here](./Abstract.md).

If there is a problem with displaying the .ipynb file here, on github, please go [here](https://nbviewer.org/github/meximized/eye_pathologies_detection_quality_estimation/blob/main/code/aberration_characteristics_final.ipynb)

## About

The main task of this project is to develop a method of estimation quality of eye pathology detection on human eye's fundus images produced by neural network.
In particular, we get an image of human fundus with some colored marked areas on it. Our purpose is to somehow visualize the information about how did neural network succeeded in finding all pathological areas on distorted image, if its performance on the source image is the 100% ideal result.

## Example of neural network image processing
| source image | moderate aberration | strong aberration |
|--------------|-------------------|-----------------|
|![src](https://user-images.githubusercontent.com/81490574/136656475-41890823-5777-42f0-ba8f-7d9cd0751d77.png) | ![1](https://user-images.githubusercontent.com/81490574/136656569-adc44d41-1703-4170-b4c8-42cddfd4ed53.png) | ![2](https://user-images.githubusercontent.com/81490574/136656571-ec886538-0174-4e1c-88d7-44183a512079.png)|

