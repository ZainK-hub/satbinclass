# satbinclass

This is the code repository for the article entitled: "Deep/Transfer Learning with Feature Space Ensemble Networks (FeatSpaceEnsNets) and Average Ensemble Networks (AvgEnsNets) for Change Detection using DInSAR Sentinel-1 and Optical Sentinel-2 Satellite Data Fusion" by Z Karim and T. van Zyl submitted to the *MDPI Remote Sensing* journal.

# Notes

- The *Combined Full Results.xlsx* file contains the full testing results.
- Download the *data.zip* file which contains the fused image data and unzip it: https://drive.google.com/file/d/1sfxayXEWubLtgp-yZbZIgFVeLYi7aO0w/view?usp=sharing 
- **Warning:** it will unzip into a size of around 8.7GB.
- Run the Conversion Notebook to package the images into the *X.npy*, *inc_res_X.npy* and *y.npy* Numpy databases which are used as the inputs to all of the other notebooks. The fused image data contains 2 x Sentinel-2 images on 1 July and 16 July 2018, one image is dropped so as to not bias the model towards the RGB data and the data is converted into a suitable format so as to avoid continually reading in the images.
- Note that *inc_res_X.npy* (for use with the InceptionResNetV2 model has an image size of 299 x 299) and *X.npy* (for use with all the other models, has an image size of 224 x 224). These files are around 6.2GB and 3.5GB large respectively.
- Running the initial Notebook will also generate the *y.npy* Numpy database of corresponding binary classification (1 or 0).
- Since two sets of experiments were run under two seed values most of the notebooks have a "Seed Value 42" and a "Seed Value 7" version. Some of the notebooks which contain the ensembles run under "Seed Value 7" may not always have all the same models run under "Seed Value 42" in that notebook purely due to avoiding redundancy since those models would be running for the second time under "Seed Value 7" since they are already contained in another "Seed Value 7" notebook.
- At an initial stage all the HybridEnsNets were also called AvgEnsNets. When it was realised that some AvgEnsNets that contain a FeatSpaceEnsNet of ResNet50 and ResNet101 (denoted as ResNet50-ResNet101 in the results file) and other single models are actually hybrid models then the naming was changed in the article. In the results the original naming is still used
- Notebooks containing the code have been added.
- The results are contained in the *model* folder.
