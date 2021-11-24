### Function 1: visualize tissue architecture 
Run the following command line to construct RGB images based on gene expression from different embedding parameters. For demonstration, please download the example data from [here](https://bmbl.bmi.osumc.edu/downloadFiles/GitHub_files/151669.zip) and put the unzip folder '151669' in the source code folder.
```
wget https://bmbl.bmi.osumc.edu/downloadFiles/GitHub_files/151669.zip 
unzip 151669.zip
python RGB_images_pipeline.py -expression 151669/151669_filtered_feature_bc_matrix.h5  -meta 151669/spatial/tissue_positions_list.csv  -scaler 151669/spatial/scalefactors_json.json -output Demo_result  -embedding scGNN  -transform logcpm 
```

#### Command Line Arguments:
*	-expression file path for raw gene expression data. [type: str]
*	-meta file path for spatial meta data recording tissue positions. [type: str]
*	-scaler file path for scale factors. [type: str]
*	-output output root folder. [type: str]
*	-embedding embedding method in use: scGNN, spaGCN, UMAP or SEDR. [type: str] [default: scGNN]
*	-transform data pre-transform method: log, logcpm or None. [type: str] [default: logcpm]


#### Results
 ```RESEPT``` stores the generative results in the following structure:
   ```
      Demo_result/
      |__RGB_images/
   ```
*	The folder 'RGB_images' stores generated RGB images of tissue architectures from different embedding parameters.  

This demo takes 25-30 mins to generate all results on the machine with a 64-core CPU.


![](./pic/Visualize/Visualize_1.png)![](./pic/Visualize/Visualize_2.png)![](./pic/Visualize/Visualize_3.png)
![](./pic/Visualize/Visualize_4.png)![](./pic/Visualize/Visualize_5.png)![](./pic/Visualize/Visualize_6.png)  

**Figure 1**| The examples of generated RGB images of tissue architectures
