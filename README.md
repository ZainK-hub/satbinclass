# satbinclass

This is the code repository for the article entitled: "Deep/Transfer Learning with Feature Space Ensemble Networks (FeatSpaceEnsNets) and Average Ensemble Networks (AvgEnsNets) for Change Detection using DInSAR Sentinel-1 and Optical Sentinel-2 Satellite Data Fusion" by Z Karim and T. van Zyl published in the *Artificial Intelligence Methods Applied to Urban Remote Sensing and GIS)* Special Issue of the *MDPI Remote Sensing* journal: https://www.mdpi.com/2072-4292/13/21/4394 

To cite: 

'''@Article{rs13214394,
AUTHOR = {Karim, Zainoolabadien and van Zyl, Terence L.},
TITLE = {Deep/Transfer Learning with Feature Space Ensemble Networks (FeatSpaceEnsNets) and Average Ensemble Networks (AvgEnsNets) for Change Detection Using DInSAR Sentinel-1 and Optical Sentinel-2 Satellite Data Fusion},
JOURNAL = {Remote Sensing},
VOLUME = {13},
YEAR = {2021},
NUMBER = {21},
ARTICLE-NUMBER = {4394},
URL = {https://www.mdpi.com/2072-4292/13/21/4394},
ISSN = {2072-4292},
ABSTRACT = {Differential interferometric synthetic aperture radar (DInSAR), coherence, phase, and displacement are derived from processing SAR images to monitor geological phenomena and urban change. Previously, Sentinel-1 SAR data combined with Sentinel-2 optical imagery has improved classification accuracy in various domains. However, the fusing of Sentinel-1 DInSAR processed imagery with Sentinel-2 optical imagery has not been thoroughly investigated. Thus, we explored this fusion in urban change detection by creating a verified balanced binary classification dataset comprising 1440 blobs. Machine learning models using feature descriptors and non-deep learning classifiers, including a two-layer convolutional neural network (ConvNet2), were used as baselines. Transfer learning by feature extraction (TLFE) using various pre-trained models, deep learning from random initialization, and transfer learning by fine-tuning (TLFT) were all evaluated. We introduce a feature space ensemble family (FeatSpaceEnsNet), an average ensemble family (AvgEnsNet), and a hybrid ensemble family (HybridEnsNet) of TLFE neural networks. The FeatSpaceEnsNets combine TLFE features directly in the feature space using logistic regression. AvgEnsNets combine TLFEs at the decision level by aggregation. HybridEnsNets are a combination of FeatSpaceEnsNets and AvgEnsNets. Several FeatSpaceEnsNets, AvgEnsNets, and HybridEnsNets, comprising a heterogeneous mixture of different depth and architecture models, are defined and evaluated. We show that, in general, TLFE outperforms both TLFT and classic deep learning for the small dataset used and that larger ensembles of TLFE models do not always improve accuracy. The best performing ensemble is an AvgEnsNet (84.862%) comprised of a ResNet50, ResNeXt50, and EfficientNet B4. This was matched by a similarly composed FeatSpaceEnsNet with an F1 score of 0.001 and variance of 0.266 less. The best performing HybridEnsNet had an accuracy of 84.775%. All of the ensembles evaluated outperform the best performing single model, ResNet50 with TLFE (83.751%), except for AvgEnsNet 3, AvgEnsNet 6, and FeatSpaceEnsNet 5. Five of the seven similarly composed FeatSpaceEnsNets outperform the corresponding AvgEnsNet.},
DOI = {10.3390/rs13214394}
}





# Notes

- The *Combined Full Results.xlsx* file contains the full testing results of all the models.
- Download the *data.zip* file which contains the fused image data and unzip it: https://drive.google.com/file/d/1sfxayXEWubLtgp-yZbZIgFVeLYi7aO0w/view?usp=sharing 
- **Warning:** it will unzip into a size of around 8.7GB.
- Run the *Conversion notebook.ipynb* to package the images into the *X.npy*, *inc_res_X.npy* and *y.npy* Numpy databases which are used as the inputs to all of the other notebooks. The fused image data contains 2 x Sentinel-2 images on 1 July and 16 July 2018, one image is dropped so as to not bias the model towards the RGB data and the data is converted into a suitable format so as to avoid continually reading in the images.
- Note that *inc_res_X.npy* (for use with the InceptionResNetV2 model has an image size of 299 x 299) and *X.npy* (for use with all the other models, has an image size of 224 x 224). These files are around 6.2GB and 3.5GB large respectively.
- Running the initial Notebook will also generate the *y.npy* Numpy database of corresponding binary classification (1 or 0).
- Since two sets of experiments were run under two seed values most of the notebooks have a "Seed Value 42" and a "Seed Value 7" version. Some of the notebooks which contain the ensembles run under "Seed Value 7" may not always have all the same models run under "Seed Value 42" in that notebook purely due to avoiding redundancy since those models would be running for the second time under "Seed Value 7" since they are already contained in another "Seed Value 7" notebook.
- At an initial stage all the HybridEnsNets were also called AvgEnsNets. When it was realised that some AvgEnsNets that contain a FeatSpaceEnsNet of ResNet50 and ResNet101 (denoted as ResNet50-ResNet101 in the results file) and other single models are actually hybrid models then the naming was changed in the article. In the results the original naming is still used
- The results are contained in the *model* folder within each subfolder.
