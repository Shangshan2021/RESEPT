# Installation

### Install dependency packages

1. Install ```PyTorch 1.5.0``` following the [official guide](https://pytorch.org/get-started/previous-versions/#linux-and-windows-9).
2. Install ```mmcv-full 1.3.0``` by running the following command:
    ```
    pip install mmcv-full==1.3.0 -f https://download.openmmlab.com/mmcv/dist/${CUDA}/torch1.5.0/index.html
    ```
    where ${CUDA} should be replaced by the specific CUDA version (cpu, cu92, cu101, cu102).

3. Install other dependencies:
    ```
    pip install -r requirements.txt
    ```
The above steps take 20-25 mins to install all dependencies.


### Install RESEPT from GitHub

```
git clone https://github.com/OSU-BMBL/RESEPT
cd RESEPT
```

