## Data preparation

### 10x Visium data

 * gene expression file: A HDF5 file stores raw gene expression data.  
 * tissue_positions_list file: A csv file contains meta information of spots including their connectivity and spatial coordinates.
 * scalefactors_json file: A json file collects the scaling factors converting spots to different resolutions.  

 More details can be found [here](https://support.10xgenomics.com/spatial-gene-expression/software/pipelines/latest/using/count).

### Annotation file (optional)

An annotation file should include spot barcodes and their corresponding annotations. It is used for evaluating predictive tissue architectures (e.g., ARI) and training user's segmentation models. The file should be named as:[sample_name]_annotation.csv. [[example]](https://bmbl.bmi.osumc.edu/downloadFiles/GitHub_files/S13_annotation.csv)

### Segmentation model file (optinal)

It is a pre-trained segmentation model file in the [pth](https://filext.com/file-extension/PTH) format, which should be provided in predicting the tissue architecture on the generative images.

### Data structure

The data schema to run our code is as follows:

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

The data schema to customize our segmentation model is as follows:

```
[training_data_folder]
|__[sample_name_1]/
|    |__spatial/
|    |    |__tissue_positions_list file
|    |    |__scalefactors_json file|
|    |__gene expression file
|    |__annotation file: [sample_name_1]_annotation.csv
|    ...
|__[sample_name_n]/
|    |__spatial/
|    |    |__tissue_positions_list file
|    |    |__scalefactors_json file|
|    |__gene expression file
|    |__annotation file: [sample_name_n]_annotation.csv  
```
