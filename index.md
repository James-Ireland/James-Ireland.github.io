---
layout: default
---


## Research interests  
* Computer Vision 
* Machine Learning 
* Artifical Inteligence  
* Robotics
* Human Robot Interaction (HRI) 
* Human Computer Interaction (HCI) 

## Datasets
### Synthetic Operating Room Table (SORT) Dataset
<img align="right" width="340" src="./Figures/sORt_img_and_annotation_stacked_vert.png">
The <a href="https://doi.org/10.7910/DVN/UCG5CW">Synthetic Operating Room Table (SORT)</a> dataset (Ireland et al. 2022) is a largescale computer vision focused on instance counting, segmentation and localisation surgical instrument depictions placed on a table. Each class contains two different 3D representations equally likely to be present for a given instance, with exception of the container class that leverages three different 3D models. In total, we generated 89,838 images, split into 60% training (53,906), 20% validation (17,965), and 20% test (17,967), containing 365,469, 121,951 and 122,142 separate object instances, respectively. 


The depictions contained are rendered using the <a href="https://www.unrealengine.com">Unreal</a> game engine and annotated leveraging the <a href="https://unrealcv.org">UnrealCV</a> plugin. SORT contains one container class, one material class (gauze) and six instrument classes namely, forceps, scalpels, pincettes (tweezers), syringes, periotomes, and scissors. To aid in generalisability, each class contains two different 3D representations equally likely to be present for a given instance, with exception of the container class that leverages three different 3D models.
  


### Multiple Sensors Multi-instance (MSMI) Dataset - available upon initial publication or request 
Multi-Sensor Multi-Instrument (MSMI) was recorded in the Human Centred Technology Research Cluster's Human Observation Laboratory at the University of Canberra (UC), being a 6.65m X 5.97m X 2.99m room, with controlled sound and lighting, for the purpose of Affective computing and HRI studies, but was repurposed for the study of medical instrument instances.MSMI, is foremost the real-world counterpart to the <a href="https://doi.org/10.7910/DVN/UCG5CW">Synthetic Operating Room Table (SORT)</a> dataset, enabling the evaluation of real-world instrument depiction counting analysis. However, MSMI is not solely just a one-for-one real-world analogy for SORT, the dataset expands its functionality by containing both depictions from various points of view (POV) within the scene and different sensors capturing these depictions, hence the multi-sensor part in the title.  
<br>
<img align="right" width="340" src="./Figures/MSMI_sample_all_feeds.PNG">
In total, MSMI contains 9 temporally synced video feeds each recording a given session at different positions within the room, with two different sensor types, <em>CMOS</em> from the Axis F1015 & the Nikon D3500 and <em>IR</em> from the Intel D315. There is a total of one hundred 15 to 30-minute sessions, in which multiple instruments were placed onto the two tables, interacted with, moved between these surfaces, occasionally dropped, intentionally carried out of the scene and in some cases brought back to be placed on one of the two tables.  
<br>
Unfortunately due to time and resource constraints, as the lead author was sole annotator, only 56 of the initial one hundred sessions have been annotated once per 5 or so frames.  While these depictions are not of any surgical operation, featuring only one human subject placing the instruments upon the table, attempts were made to make the placement of instances as varied as possible, given these limitations. Namely, the person being observed, the lead author, tried their best to vary interactions, via their handedness (left vs. right), movement speed, hand coverings (bare skin vs. white gloves vs. purple gloves) and targeted placement (neat individual tool layout vs. messy piles unthoughtfully dumped). 
<br>
<br>
<img align="right" width="340" src="./Figures/MSMI_distribution.PNG">
To annotate this dataset a new MATLAB based annotation tool was leveraged, creatively named the '<a href="https://github.com/James-Ireland/Muilt_view_Annotation_Tool">Muilt_view_Annotation_Tool</a>', containing code inspired by early work of crowd counting in their use of homogeneous transforms to annotate in a single-view and have those annotations projected in other views, to be later refined. Specifically, we leveraged the homogeneous transform method published by Hartley, and Zisserman in their book `<cite>Multiple view geometry in computer vision</cite>' (2003, Hartley & Zisserman), which they kindly provided their code as <a href="https://www.robots.ox.ac.uk/~vgg/hzbook/code">supplementary material</a>. 
<br>
<br>
Each instance annotation attribute of a medical instrument or material (i.e. polygon or bounding box), is actually made up of a list of several, each individual entry being that value specific to one of the nine different camera POV depictions. For which only the RGB feed in each was annotated, since in the case of the RGB-D sensors each depth image is already matched pixel-wise to their RGB pair, and so additionally annotating the depth feed would be redundant. Currently only three of the 9 views (Camera 5, 6, and 7) have annotations that are pixel-wise accuract due to the homography transforms needing manual refinements, but hopefully future versions of this dataset will have these changes made and the missing annotations for the 44 untouched videos addressed. 
<br>
<br>
Hartley, R. and Zisserman, A., 2004. Two-view geometry. Multiple View Geometry in Computer Vision, pp.237-238., <a href="https://doi.org/10.1017/CBO9780511811685"> doi.org/10.1017/CBO9780511811685 </a>

## Code 
 &nbsp;
  * <a href="https://github.com/James-Ireland/Synthetic_OR_table_generative_game">Link to our game with custom UnrealCV plug-in </a>
  
  * <a href="https://github.com/James-Ireland/Surgical_instrument_instance_counting_benchmarks">Link to the SORT dataset benchmarking code </a>
  
  * <a href="https://github.com/James-Ireland/Muilt_view_Annotation_Tool">Link to our annotation tool 'Muilt_view_Annotation_Tool' for the MSMI dataset </a>
 
&nbsp;

## Publications
```bibtex

@inproceedings{RN12661,
   author = {Ireland, James and Radwan, Ibrahim and Herath, Damith and Goecke, Roland},
   title = {Can Synthetic Data Improve Multi-Class Counting of Surgical Instruments?},
   booktitle = {2022 International Conference on Digital Image Computing: Techniques and Applications (DICTA)},
   publisher = {IEEE},
   pages = {1-8},
   abstract = {Counting is a common preventative measure taken to ensure surgical instruments are not retained during surgery, which could cause serious detrimental effects including chronic pain and sepsis. 
   A hybrid human-AI system could support or partially automate this manual counting of instruments. 
   An important element to evaluate the viability of using deep learning computer vision-based counting is a suitable large-scale dataset of surgical instruments. 
   Other domains, such as crowd analysis and instance counting, have leveraged synthetic datasets to evaluate and augment different approaches. 
   We present a synthetic dataset (SORT), which is complemented by a smaller real-world dataset of surgical instruments (MSMI), to assess the hypothesis of whether synthetic training data can improve the performance of multi-class multi-instance counting models when applied to real-world data. 
   In this preliminary study, we provide comparative baselines for various popular counting techniques on synthetic data, such as direct regression, segmentation, localisation, and density estimation. 
   These experiments are repeated at different resolutions – full high-definition (1080×1920 pixels), half (690×540 pixels), and a quarter (480×270 pixels) – to measure the robustness of different supervision methods to varying image scales. 
   The results indicate that neither the degree of supervision nor the image resolution during model training impact performance significantly on the synthetic data. 
   However, when testing on the real-world instrument dataset, the models trained on synthetic data were significantly less accurate. 
   These results indicate a need for further work in either the refinement of the synthetic depictions or fine-tuning upon real-world data to achieve similar performance in domain adaptation scenarios compared to training and testing solely on the synthetic data.},
   DOI = {10.1109/DICTA56598.2022.10034591},
   url = {https://ieeexplore.ieee.org/document/10034591},
   type = {Conference Proceedings}
}

@inproceedings{RN12736,
   author = {Ahmad, Dua’a and Goecke, Roland and Ireland, James},
   title = {CNN Depression Severity Level Estimation from Upper Body vs. Face-Only Images},
   series = {Pattern Recognition. ICPR International Workshops and Challenges},
   publisher = {Springer International Publishing},
   pages = {744-758},
   abstract = {Upper body gestures have proven to provide more information about a person’s depressive state when added to facial expressions. 
   While several studies on automatic depression analysis have looked into this impact, little is known in regard to how a convolutional neural network (CNN) uses such information for predicting depression severity levels. 
   This study investigates the performance in various CNN models when looking at facial images alone versus including the upper body when estimating depression severity levels on a regressive scale. 
   To assess generalisability of CNN model performance, two vastly different datasets were used, one collected by the Black Dog Institute and the other being the 2013 Audio/Visual Emotion Challenge (AVEC). 
   Results show that the differences in model performance between face versus upper body are slight, as model performance across multiple architectures is very similar but varies when different datasets are introduced.},
   ISBN = {978-3-030-68780-9},
   type = {Conference Proceedings}
}

@inproceedings{RN12737,
   author = {Hinwood, David and Ireland, James and Jochum, Elizabeth Ann and Herath, Damith},
   title = {A Proposed Wizard of OZ Architecture for a Human-Robot Collaborative Drawing Task},
   series = {Social Robotics},
   publisher = {Springer International Publishing},
   pages = {35-44},
   abstract = {Researching human-robot interaction “in the wild” can sometimes require insight from different fields. 
   Experiments that involve collaborative tasks are valuable opportunities for studying HRI and developing new tools. 
   The following describes a framework for an “in the wild” experiment situated in a public museum that involved a Wizard of OZ (WOZ) controlled robot. 
   The UR10 is a non-humanoid collaborative robot arm and was programmed to engage in a collaborative drawing task. 
   The purpose of this study was to evaluate how movement by a non-humanoid robot could affect participant experience. 
   While the current framework is designed for this particular task, the control architecture could be built upon to provide a base for various collaborative studies.},
   ISBN = {978-3-030-05204-1},
   type = {Conference Proceedings}
}

``` 


