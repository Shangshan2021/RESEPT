## System Requirements

### Hardware Requirements

```RESEPT``` was trained on a standard computer with a 64-core CPU, 20G RAM, and a GPU with 11G VRAM. The function of customizing the segmentation model only can run on GPU device now. Other functions for RESEPT need the minimum requirements of a CPU with 8 cores and 8G RAM.

### Software Requirements

#### OS Requirements

RESEPT can run on Linux. The package has been tested on the following system:

* Linux: Ubuntu 20.04

#### Python Dependencies

``` RESEPT ``` mainly depends on the Python (3.6+) scientific stack.

``` 
scipy==1.6.2
networkx==2.5.1
opencv_contrib_python==4.5.1.48
tqdm==4.60.0
scikit_image==0.18.1
numpy==1.19.2
umap_learn==0.5.1
six==1.15.0
matplotlib==3.3.4
terminaltables==3.1.0
torch==1.5.0
scanpy==1.7.2
statsmodels==0.12.2
requests==2.25.1
munkres==1.1.4
mmcv_full==1.3.0
rpy2==3.1.0
pandas==1.2.3
numba==0.53.1
seaborn==0.11.1
anndata==0.7.6
cityscapesscripts==2.2.0
leidenalg==0.8.7
Pillow==8.3.1
python_igraph==0.9.6
scikit_learn==0.24.2
umap==0.1.1
```
