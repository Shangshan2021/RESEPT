## Data preparation

### 10x Visium data

 * gene expression file: A HDF5 file stores raw gene expression data.  
 * tissue_positions_list file: A csv file stores meta of spot including their connectivity and spatial coordinates.
 * scalefactors_json file: A json file stores the scaling factors converting spots to different resolutions.

### Annotation file

An annotation file recording spot barcodes and their corresponding annotations. It is required in the functions of evaluating predictive tissue architectures and customizing segmentation model. The file should be named as: [sample_name]_annotation.csv. [[example]](https://bmbl.bmi.osumc.edu/downloadFiles/data_and_model/data_and_model.zip) (/ocean/projects/ccr180012p/shared/Demo/S13/S13_annotation.csv)

### Segmentation model file

A trained segmentation model file in pth format. It is required to predict tissue architecture on the generative visuals.

### Data structure

The data schema to run our code is as following:

```
[sample_name]/
 |__spatial/
 |    |__tissue_positions_list file
 |    |__scalefactors_json file
 |__gene expression file
 |__annotation file: [sample_name]_annotation.csv (optional)

model/ (optional)
 |__segmentation model file 
```
