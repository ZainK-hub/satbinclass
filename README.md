# satbinclass

This is the code repository for the article entitled: "Deep/Transfer Learning with Feature Space Ensemble Networks (FeatSpaceEnsNets) and Average Ensemble Networks (AvgEnsNets) for Change Detection using DInSAR Sentinel-1 and Optical Sentinel-2 Satellite Data Fusion" by Z Karim and T. van Zyl.

# Notes

- Download the *data.zip* file which contains the fused image data and unzip it: https://drive.google.com/file/d/1sfxayXEWubLtgp-yZbZIgFVeLYi7aO0w/view?usp=sharing 
- **Warning:** it will unzip into a size of around 8.7GB.
- Run the Conversion Notebook to package the images into the *X.npy*, *inc_res_X.npy* and *y.npy* Numpy databases which are used as the inputs to all of the other notebooks. The fused image data contains 2 x Sentinel-2 images on 1 July and 16 July 2018, one image is dropped so as to not bias the model towards the RGB data and the data is converted into a suitable format so as to avoid continually reading in the images.
- Note that *inc_res_X.npy* (for use with InceptionResNetV2 has an image size of  x ) and *X.npy* (for use with all the other models, has an image size of 224x224) will be around 6.2GB and 3.5GB large respectively.
- Running the initial Notebook will also generate the *y.npy* Numpy database of corresponding binary classification (1 or 0).
- At an initial stage all the HybridEnsNets were also called AvgEnsNets. When it was realised that some AvgEnsNets that contain a FeatSpaceEnsNet of ResNet50 and ResNet101 (denoted as ResNet50-ResNet101 in the results file) and other single models are actually hybrid models then the naming was changed in the article. In the results the original naming is still used
- Will add the Notebooks containing the code, they just need to be cleaned up though.
- The results are contained in the *model* folder.
- Apologies, there was an error in the 1st submission of the article, in *Table 1 Ensemble definitions* on pg. 10 all of the *HybridEnsNet* models include *FeatSpaceEnsNet 3* (*ResNet50-ResNet101*) and not *FeatSpaceEnsNet 6*.

