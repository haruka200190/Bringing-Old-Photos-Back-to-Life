#◢ Implementation of Photo Restoration

* All code fils have been copied and modified from the following repositories:
https://github.com/microsoft/Bringing-Old-Photos-Back-to-Life

## How to run the code:
  * Open main.pynb and run through the cells but skip the training part.
  * If you want to see the result before modification, follow the instruction in the "Set up the environment" section.
  * The training part is incomplete, so just view the pynb log if datasets are not ready.  
  
## Modified terms
  * add directory [training_data] with following structure:
    * Real_L_old
      * [scratched photos from humanface8000 (excluded according to Gradescope pokicy) ]
    * Real_RGB_old
      * [images from humanface8000 (excluded according to Gradescope pokicy) ]
    * VOC_RGB_JPEGImages
      * [images from Pascal VOC dataset (excluded according to Gradescope pokicy) ]
    * bigfiles
      * [output for created files from Create_Bigfile.py (excluded according to Gradescope pokicy) ]
    * ckpt
      * [saving checkpoint for model training]
    * opt
      * [output directory for model training]
  * Create_Bigfile.py
    * Path: /Global/data/Create_Bigfile.py
    * Modified the path of input and output directory.
    * Changed the name of target folders **VOC** -> **VOC_RGB_JPEGImages**
    * Modified the inticating number that prints the progress of writing files (i%1000 -> i%100) 
  * online_dataset_for_old_photos.py
      * Path: /Global/data/online_dataset_for_old_photos.py
    * Modified the iteration of filter loop to restrict the number of filtered images
  * main.pynb
      * modified the file link in environment setting section
    * add "Train the model" section. Since the training is incomplete, some error logs are recorded

## Datasets: 
  * [Pascal VOC](http://host.robots.ox.ac.uk:8080/)(only used for training)
      * source: http://host.robots.ox.ac.uk:8080/

    * extract the images in **JPEGImages** and save them in **VOC_RGB_JPEGImages**
  * [humanface8000](https://www.kaggle.com/datasets/bharatadhikari/humanface8000/)(only used for training)
      * source: https://www.kaggle.com/datasets/bharatadhikari/humanface8000/

    * extract and save the images from **gray** into **Real_L_old**, and the images from "color" into **Real_RGB_old**
  * test_images for displaying test results
    * path: /test_images
