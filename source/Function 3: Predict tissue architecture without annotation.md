### Function 3: predict tissue architecture without annotation
Run the following command line to generate RGB images based on gene expression from different embedding parameters and predict tissue architectures with top-5 Moran's I. For demonstration, please download the example data from [here](https://bmbl.bmi.osumc.edu/downloadFiles/GitHub_files/151669.zip) and the pre-trained model from [here](https://bmbl.bmi.osumc.edu/downloadFiles/GitHub_files/model_151669.zip). Then put unzip folders '151669' and '151669' in the source code folder.
```
wget https://bmbl.bmi.osumc.edu/downloadFiles/GitHub_files/151669.zip 
wget https://bmbl.bmi.osumc.edu/downloadFiles/GitHub_files/model_151669.zip 
unzip model_151669.zip
unzip 151669.zip
python test_pipeline.py -expression 151669/151669_filtered_feature_bc_matrix.h5  -meta 151669/spatial/tissue_positions_list.csv  -scaler 151669/spatial/scalefactors_json.json -k 7 -model model_151669/151669_scGNN.pth -output Demo_result_tissue_architecture  -embedding scGNN  -transform logcpm -device cpu
```

#### Command Line Arguments:
*	-expression file path for raw gene expression data. [type: str]
*	-meta file path for spatial meta data recording tissue positions. [type: str]
*	-scaler file path for scale factors. [type: str]
*	-k the number of tissue architectures(setting -1 will recommend a K for you). [type: int] [default: 7]
*	-model file path for pre-trained model. [type: str]
*	-output output root folder. [type: str]
*	-embedding embedding method in use: scGNN, spaGCN, UMAP or SEDR. [type: str] [default: scGNN]
*	-transform data pre-transform method: log, logcpm or None. [type: str] [default: logcpm]
*	-device cpu/gpu device option: cpu or gpu. [type: str] [default: cpu]

#### Results
 ```RESEPT``` stores the generative results in the following structure:
   ```
   Demo_result_tissue_architecture/
   |__RGB_images/
   |__segmentation_test/
         |__segmentation_map/
         |__top5_MI_value.csv
   ```
*	The folder 'RGB_images' contains the generated RGB images of tissue architectures from different embedding parameters.
*	The folder 'segmentation_map' stores the predicted tissue architectures with top-5 Moran's I.
*	The file 'top5_MI_value.csv' records Moran's I value corresponding to the tissue architectures.  

This demo takes 30-35 mins to generate all the results on the machine with a 64-core CPU.

- ![](./pic/Predict/1.png)![](./pic/Predict/segmentation/1.png)  
- ![](./pic/Predict/2.png)![](./pic/Predict/segmentation/2.png)  
- ![](./pic/Predict/3.png)![](./pic/Predict/segmentation/3.png)  
- ![](./pic/Predict/4.png)![](./pic/Predict/segmentation/4.png)  
- ![](./pic/Predict/5.png)![](./pic/Predict/segmentation/5.png)  
 
![](./pic/Predict/pre.png)

**Figure 5**| The generated RGB images of tissue architectures and predicted tissue architectures with top-5 Moran???s I, and corresponding Moran???s I value (k=7).


- ![](./pic/Evaluate/k=5/images/1.png)![](./pic/Evaluate/k=5/1.png)  
- ![](./pic/Evaluate/k=5/images/2.png)![](./pic/Evaluate/k=5/2.png)
- ![](./pic/Evaluate/k=5/images/3.png)![](./pic/Evaluate/k=5/3.png)
- ![](./pic/Evaluate/k=5/images/4.png)![](./pic/Evaluate/k=5/4.png)
- ![](./pic/Evaluate/k=5/images/5.png)![](./pic/Evaluate/k=5/5.png)

**Figure 6**| The generated RGB images of tissue architectures and predicted tissue architectures with top-5 Moran???s I (k=5).


- ![](./pic/Evaluate/k=8/images/1.png)![](./pic/Evaluate/k=8/1.png)  
- ![](./pic/Evaluate/k=8/images/2.png)![](./pic/Evaluate/k=8/2.png) 
- ![](./pic/Evaluate/k=8/images/3.png)![](./pic/Evaluate/k=8/3.png) 
- ![](./pic/Evaluate/k=8/images/4.png)![](./pic/Evaluate/k=8/4.png) 
- ![](./pic/Evaluate/k=8/images/5.png)![](./pic/Evaluate/k=8/5.png) 

**Figure 7**| The generated RGB images of tissue architectures and predicted tissue architectures with top-5 Moran???s I (k=8).
 
