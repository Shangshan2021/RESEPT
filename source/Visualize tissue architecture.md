### Visualize tissue architecture 

Run the following command line to generate visuals of gene expression from different embedding parameters. For demonstration, please download the example data from [here](https://bmbl.bmi.osumc.edu/downloadFiles/data_and_model/data_and_model.zip)(/ocean/projects/ccr180012p/shared/Demo/S13) and put the unzip folder 'S13' to source code folder.

```
wget https://bmbl.bmi.osumc.edu/downloadFiles/RESEPT/RESEPT.zip 
unzip RESEPT.zip
python RGB_images_pipeline.py -expression S13/S13_filtered_feature_bc_matrix.h5  -meta S13/spatial/tissue_positions_list.csv  -scaler S13/spatial/scalefactors_json.json -output Demo_result  -embedding scGNN  -transform logcpm 
```

#### Command Line Arguments:

*	-expression file path for raw gene expression data. [type:str]
*	-meta file path for spatial meta recording tissue positions. [type:str]
*	-scaler file path for scale factors. [type:str]
*	-output output root folder. [type:str]
*	-embedding embedding method in use: scGNN or spaGCN. [type:str]
*	-transform data pre-transform method: log, logcpm or None. [type:str]

#### Results

 ```RESEPT``` stores the generative results in the following structure:

   ```
   Demo_result/
   |__RGB_images/
   ```

*	The folder 'RGB_images' stores generative visuals of tissue architectures from different embedding parameters. 
*	This Demo takes 25-30 mins to generate all results on a machine with 64-core CPU.
*	An example of generative visuals of tissue architectures is shown below:

![](./pic/Customize_segmentation_1.png)
