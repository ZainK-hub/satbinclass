# satbinclass
# Notes

- Download the data.zip file which contains the fused image data and unzip it: https://drive.google.com/file/d/1sfxayXEWubLtgp-yZbZIgFVeLYi7aO0w/view?usp=sharing 
- **Warning:** it will unzip into a size of around 8.7GB.
- Run the Conversion Notebook to package the images into the *X.npy*, *inc_res_X.npy* and *y.npy* Numpy databases which are used as the inputs to all of the other notebooks. The fused image data contains 2 x Sentinel-2 images on 1 July and 16 July 2018, one image is dropped so as to not bias the model towards the RGB data and the data is converted into a suitable format.
- Note that *inc_res_X.npy* (for use with InceptionResNetV2 has an image size of  x ) and *X.npy* (for use with all the other models, has an image size of 224x224) will be around 6.2GB and 3.5GB large respectively.
- Running the initial Notebook will also generate the y.npy files.
- At an initial stage all the HybridEnsNets were also called AvgEnsNets. When it was realised that some AvgEnsNets that contain a FeatSpaceEnsNet and other models      -are actually hybrid models then the naming was changed.
- Will add the Notebooks containing the code, they just need to be cleaned up though.
GB 
