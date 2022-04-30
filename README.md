# Important points while doing installation of Detectron 2

```
*Whenver you are installing detectron2 you need to check the pytorch version and check if you are using CPU/GPU(What is your CUDA version?)
```
# To check the GPU and Cuda Cersion

```
nvidia-smi
nvcc --version
```

# To install the pytorch, torchvision and CUDA versions

```
conda install pytorch==1.6 torchvision cudatoolkit=10.0 -c pytorch
pip install cython
conda install git
pip install "git+https://github.com/philferriere/cocoapi.git#egg=pycocotools&subdirectory=PythonAPI"
pip install pycocotools-windows
git clone https://github.com/augmentedstartups/detectron2
cd detectron2
pip install -e .
pip install opencv-python
python tests/test_windows_install.py
```
