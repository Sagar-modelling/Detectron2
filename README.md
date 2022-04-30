# Important points while doing installation of Detectron 2

```
*Whenver you are installing detectron2 you need to check the pytorch version and check if you are using CPU/GPU(What is your CUDA version?)

*Download and install Cuda-10.1 (pytorch 1.4, 1.5, 1.6):
https://developer.nvidia.com/cuda-10.1-download-archive-base

```
# To check the GPU and Cuda Cersion

```
nvidia-smi
nvcc --version
```

# To install the pytorch, torchvision and CUDA versions

```
conda create -n detectron python=3.7
conda install pytorch==1.6 torchvision cudatoolkit=10.0 -c pytorch
pip install cython
pip install "git+https://github.com/philferriere/cocoapi.git#egg=pycocotools&subdirectory=PythonAPI"
pip install pycocotools-windows
git clone https://github.com/augmentedstartups/detectron2
cd detectron2
pip install -e .
pip install opencv-python
python tests/test_windows_install.py
```
