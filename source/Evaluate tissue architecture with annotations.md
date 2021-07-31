### Evaluate tissue architecture with annotations

Run the following command line to generate RGB images from different embedding parameters, segmentation maps with top5 Moran's I and their evaluation metrics.
Please download the corresponding pre-trained model from [click here for downloading data and model](https://bmbl.bmi.osumc.edu/downloadFiles/data_and_model/data_and_model.zip) and put it in the specified folder.

```
wget https://bmbl.bmi.osumc.edu/downloadFiles/RESEPT/RESEPT.zip 
unzip RESEPT.zip
python evaluation_pipeline.py -matrix Demo/S13/S13_filtered_feature_bc_matrix.h5  -csv Demo/S13/spatial/tissue_positions_list.csv  -json Demo/S13/spatial/scalefactors_json.json -out Demo_result  -method scGNN  -transform logcpm -label Demo/S13.csv -checkpoint Demo/checkpoint/S13_scGNN.pth
```

#### Command Line Arguments:

*	-matrix specify path for raw gene expression data provided by 10X in h5 file. [type:str]
*	-csv specify path for meta file recording tissue positions provided by 10x in csv file. [type:str]
*	-json specify path for scale factors provided by 10x in json file. [type:str]
*	-label specify path for annotation file recording cell barcodes and their annotations, which is used for calculating ARI. [type:str]
*	-checkpoint specify path for pretrained model file. [type:str]
*	-out specify output root folder. [type:str]
*	-method specify embedding method in use: scGNN or spaGCN. [type:str]
*	-transform specify data pre-transform: log, logcpm or None. [type:str]

#### Expected Results

RESEPT stores the generative results in the following structure:

   ```
   Demo_result/
   |__RGB_images/
   |__segmentation_evaluation/
         |__segmentation_map/
         |__top5_evaluation.csv
   ```

*	-The folder 'RGB_images' stores generative RGB images form different embedding parameters. 
*	-The folder 'segmentation_map' stores visuals of segmentation results with top5 Moran's I. 
*	-The file 'top5_evaluation.csv' records various evaluation metrics corresponding to segmentation results with top5 Moran's I .
*	-This Demo takes 30-35 mins to generate all results on a machine with a multi-core CPU.
*	-The generative visual of gene expression, segmentation map and its evaluation metric of best result among top5 Moran's I are shown below:
![](./pic/Evaluate_predictive_1.png) ![](./pic/Evaluate_predictive_2.png)
