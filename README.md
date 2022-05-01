# Important points while doing installation of Detectron 2 in Ubuntu 18.04

```
*Whenver you are installing detectron2 you need to check the pytorch version and check if you are using CPU/GPU(What is your CUDA version?)

*Download and install Cuda-10.1 (pytorch 1.4, 1.5, 1.6):
https://developer.nvidia.com/cuda-10.1-download-archive-base

sudo apt-get update
sudo apt-get upgrade

Go to official website NVIDIA for CUDA 10.1 (https://developer.nvidia.com/cuda-10.1-download-archive-base). 
Here select Linux => x86_64 => Ubuntu => 18.04 => runfile(local). After that, the file will start downloading. 
sudo sh cuda_10.1.105_418.39_linux.run

sudo nano ~/.bashrc
Add those lines to the end of file:
export PATH=/usr/local/cuda-10.1/bin${PATH:+:${PATH}}
export LD_LIBRARY_PATH=/usr/local/cuda-10.1/lib64${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}

source ~/.bashrc
Now go to download cuDNN 7.5.1. For that visit site (https://developer.nvidia.com/rdp/cudnn-archive). Log in or register there.
Choose Download cuDNN v7.5.1 (April 22, 2019), for CUDA 10.1.

After downloading unzip that cudnn-10.1-linux-x64-v7.5.1.10.tgz
Then just copy those files to your cuda directory using those commands
sudo cp cuda/include/cudnn.h /usr/local/cuda/include/
sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64/

Add permisions
sudo chmod a+r /usr/local/cuda/include/cudnn.h
sudo chmod a+r /usr/local/cuda/lib64/libcudnn*
```

# Install cmake-gui
```
Ubuntu 18: Download and compile CMake-gui from source. The default CMake-gui version (3.10) installed via sudo apt-get install cmake-qt-gui provokes some compiling errors. Required CMake version >= 3.12.
Uninstall your current Cmake-gui version by running sudo apt purge cmake-qt-gui.
Install OpenSSL for building CMake by running sudo apt install libssl-dev.
Run sudo apt-get install qtbase5-dev.
Download the Latest Release of CMake Unix/Linux Source from the CMake download website, called cmake-X.X.X.tar.gz.
Unzip it and go inside that folder from the terminal.
Run ./configure --qt-gui. Make sure no error occurred.
Run ./bootstrap && make -j`nproc` && sudo make install -j`nproc`. Make sure no error occurred.
Assuming your CMake downloaded folder is in {CMAKE_FOLDER_PATH}, every time these instructions mentions cmake-gui, you will have to replace that line by {CMAKE_FOLDER_PATH}/bin/cmake-gui

```

# To check the GPU and Cuda Version

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
