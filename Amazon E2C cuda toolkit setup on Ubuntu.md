Amazon_E2C_cuda_toolkit_setup on Ubuntu
========================================

This script will help in just quicking the process of setting up the nvidia with cuda setup. It involves install cuda-toolkit that will install the cuda and its comapatible nvidia driver.

Step-1: Check the GPU device in your system
```
sudo lshw -C display
```

Step-2: Check the Linux distro installed
```
lsb_release -a
```

Step-3: On the [cuda download website](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu&target_version=22.04&target_type=runfile_local) choose the toolkit as per your platform. 
Suppose we get the recommendation of "cuda_11.8.0_520.61.05_linux.run". Run the command to download the driver and then installing the driver.
```
wget https://developer.download.nvidia.com/compute/cuda/11.8.0/local_installers/cuda_11.8.0_520.61.05_linux.run

sudo sh cuda_11.8.0_520.61.05_linux.run
```
If the installation fails and you get error something similar 'gcc' or 'cc' or 'make' from after going through '/var/log/cuda-installer.log' and '/var/log/nvidia-installer.log'.
Then run the try you needs some 'build-essential' tools neccessary for '.run' files. 
```
sudo apt install build-essential
```
Now try to reinstall the cuda 
```
sudo sh cuda_11.8.0_520.61.05_linux.run
```

Step-4: Add the following path at the end of the ~/.bashrc file.
```
export PATH=/usr/local/cuda-11.8/bin:$PATH
export LD_LIBRARY_PATH=usr/local/cuda-11.8/lib6:$LD_LIBRARY_PATH
```

Step-5: Reload the ~/.bashrc file.
```
source ~/.bashrc
```

Done!!
