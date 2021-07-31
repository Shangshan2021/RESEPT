### Customize segmentation model 

RESEPT supports fine-tuning our segmentation model by using your own 10x data. Organize all 10x data and their labels according to our predefined data schema and download our pre-trained model from [here](a new link). The 10x data of each sample should be located in a separate sub-folder under the 'data' folder. Specify the downloaded model file path and run the following command line to get the RGB images of your own data and the customized model.  

```
wget https://bmbl.bmi.osumc.edu/downloadFiles/RESEPT/RESEPT.zip 
unzip RESEPT.zip
python training_pipeline.py -data_folder Demo -output Demo_result -embedding scGNN  -transform logcpm -model Demo/checkpoint/S13_scGNN.pth
```

#### Command Line Arguments:

* -data_folder 10X data h5 file, tissue positions list file, scale factors json file and label file folder path. [type:str]
* -model specify path for pretrained model file. [type:str]
* -output specify output root folder. [type:str]
* -embedding specify embedding method in use: scGNN or spaGCN. [type:str]
* -transform specify data pre-transform: log, logcpm or None. [type:str]

#### Expected Results

RESEPT stores the generative results in the following structure:

   ```
   Demo_result/
   |__RGB_images/
   |__RGB_images_label/
   work_dirs/
   |__config/
         |__epoch_n.pth
   ```

*	-The folder 'RGB_images' stores generative RGB images of input 10x data from different embedding parameters. 
*	-The folder 'RGB_images_label' stores their labeled category maps according to input label file. 
*	-The file 'epoch_n.pth' is the customized model.
*	-This Demo takes about 3 hours to generate the model on a machine with a 2080Ti GPU.
*	-An example of generative visuals of tissue architectures and its label image are shown below:

![](./pic/Customize_segmentation_1.png) ![](./pic/Customize_segmentation_2.png)
