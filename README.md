# SYDE675-ReproducibilityChallenge-2022
SYDE675-Final Report and Code

## Unsupervised Learning of Probably Symmetric Deformable 3D Objects from Images in the Wild

### Summary
The following report for final project (reproducibility challenge) for SYDE-675 is based on the paper titled 'Unsupervised Learning of Probably Symmetric Deformable 3D Objects from Images in the Wild' by Shangzhe Wu et al., and Visual Geometry Group, University of Oxford [1]. The paper presents a model that learns 3D reconstruction without external supervision and uses an unconstrained collection of single-view images, therefore not requiring multiple views of the same instance. The model is trained on single-view images of a deformable object category and produces as output a deep network that can estimate the 3D shape of any instance given a single image of it. 

What we aid to reproduce, inspired by the CVPR paper is substituting autoencoders for a classic machine learning technique, PCA, to reconstruct a 3D deformable object given a collection of a fixed view image under varying lighting condition. Common 3D reconstruction include shape from shading and photometric stereo. Shape from shading assumes a shading model such as Lambertian reflectance and reconstructs the surface by exploiting the non-uniform illumination. Constructing principal components for a single viewpoint under varying illuminations allows for creating a low-dimensional generative model to explain lighting variability.  Used on the same human face with different lighting conditions, the dominant eigenvectors do not reflect facial shape but lighting conditions. We are not using complex illumination for photometric properties.  Hallman et al. concluded that 5 eigenvectors would be sufficient to model frontal images under arbitrary illuminations. These linear subspaces correspond to frontal lighting, side lighting, lighting from above/below, extreme side lighting and lighting from a corner. 

### Code 
The code for the original [Demo](https://github.com/elliottwu/unsup3d/blob/master/demo/demo.py) and [utils](https://github.com/elliottwu/unsup3d/blob/master/demo/utils.py) was reused from an implementation by [elliottwu](https://github.com/elliottwu/unsup3d)

 The code for the ML based techinque was reused from 
 
 

Listed code repositories are MIT-licensed as open-source for academic research.

### Dataset 

We used the pretrained weights provided in the open-source repo. The weights were obtained by the author of the using the following datasets. 

CelebA face dataset - click [here](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html)

Synthetic face dataset generated using Basel Face Model - click [here](https://faces.dmi.unibas.ch/bfm/)

Cat face dataset - click [here](https://academictorrents.com/details/c501571c29d16d7f41d159d699d0e7fb37092cbd)

Synthetic car dataset generated from ShapeNet cars - click [here](https://shapenet.org/)


For the implementation of the PCA technique we have used the following dataset

Yale Face Dataset for PCA - click [here](http://vision.ucsd.edu/~leekc/ExtYaleDatabase/ExtYaleB.html)




### Reference 
1. Wu, S., Rupprecht, C., & Vedaldi, A. (2020). Unsupervised learning of probably symmetric deformable 3d objects from images in the wild. In Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (pp. 1-10).
2. "the Exteded Yale Face Database B" and reference Athinodoros Georghiades, Peter Belhumeur, and David Kriegman's paper, "From Few to Many: Illumination Cone Models for Face Recognition under Variable Lighting and Pose", PAMI, 2001,
