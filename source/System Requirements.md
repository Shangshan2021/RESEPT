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
numpy 1.18.1
torch 1.4.0
networkx 2.4
pandas 0.25.3
matplotlib 3.1.2
seaborn 0.9.0
umap-learn 0.3.10
munkres 1.1.2
tqdm 4.48.0
python-igraph 0.8.3
scanpy 1.7.2
scikit-image 0.18.1
opencv-python 4.5.1.48
louvain  0.7.0
anndata 0.7.6
mmcv-full  1.3.0
mmsegmentation 0.12.0
```
