### Function 1: visualize tissue architecture 
Run the following command line to construct RGB images based on gene expression from different embedding parameters. For demonstration, please download the example data from [here](https://bmbl.bmi.osumc.edu/downloadFiles/GitHub_files/S10.zip) and put the unzip folder 'S10' in the source code folder.
```
wget https://bmbl.bmi.osumc.edu/downloadFiles/GitHub_files/S10.zip 
unzip S10.zip
python RGB_images_pipeline.py -expression S10/S10_filtered_feature_bc_matrix.h5  -meta S10/spatial/tissue_positions_list.csv  -scaler S10/spatial/scalefactors_json.json -output Demo_result  -embedding scGNN  -transform logcpm 
```

#### Command Line Arguments:
*	-expression file path for raw gene expression data. [type: str]
*	-meta file path for spatial meta data recording tissue positions. [type: str]
*	-scaler file path for scale factors. [type: str]
*	-output output root folder. [type: str]
*	-embedding embedding method in use: scGNN or spaGCN. [type: str] [default: scGNN]
*	-transform data pre-transform method: log, logcpm or None. [type: str] [default: logcpm]


#### Results
 ```RESEPT``` stores the generative results in the following structure:
   ```
      Demo_result/
      |__RGB_images/
   ```
*	The folder 'RGB_images' stores generated RGB images of tissue architectures from different embedding parameters.  

This demo takes 25-30 mins to generate all results on the machine with a 64-core CPU.
The examples of generative visuals of tissue architectures are shown below:

![](./pic/Visualize/Visualize_1.png)![](./pic/Visualize/Visualize_2.png)![](./pic/Visualize/Visualize_3.png)
![](./pic/Visualize/Visualize_4.png)![](./pic/Visualize/Visualize_5.png)![](./pic/Visualize/Visualize_6.png)  

**Figure 1**| The examples of generative visuals of tissue architectures
