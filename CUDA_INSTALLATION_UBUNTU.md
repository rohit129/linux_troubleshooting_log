### CUDA INSTALLATION WITH COMPATIBLE NVIDIA DRIVER

Cuda toolkit comes with the compatible nvidia driver therefore it is better to remove the any existing nvidia driver otherwise some compatilibilty issues will be faced in installation.

**Step-1:** Remove the previous nvidia driver.
```
sudo apt-get remove --purge nvidia\*
sudo apt-get autoremove
```

**Step-2:** [Disable Nouveau driver](https://docs.nvidia.com/cuda/cuda-installation-guide-linux/index.html#runfile-nouveau)

Reboot the system


**Step-3:** Download the [cuda toolkit](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Ubuntu)

**Step-4:** Follow the below simple steps to install mentioned in the [Link](https://unix.stackexchange.com/questions/440840/how-to-unload-kernel-module-nvidia-drm)

![image](https://user-images.githubusercontent.com/13540412/146391471-37851466-94cc-43ad-ac41-91639411d90b.png)

**Step-5:** Add the path to *~/.bashrc*
```
export PATH="/usr/local/cuda/bin:$PATH"
export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda/lib64"
```

**Step-6:** Open a new terminal and run command to check it once
```
$ nvidia-smi
$ nvcc --version
```
**Step-7:** [To fully Verify the cuda](https://xcat-docs.readthedocs.io/en/stable/advanced/gpu/nvidia/verify_cuda_install.html)

Enjoy CUDA 👍 !!

---

### Also install CUDNN
Step a: [CUDNN download and install](https://docs.nvidia.com/deeplearning/cudnn/install-guide/index.html#download)

Step b: Verify the CUDNN see the [Link](https://stackoverflow.com/questions/31326015/how-to-verify-cudnn-installation)

![cudnn_verify](https://user-images.githubusercontent.com/13540412/146490423-e4facd1d-1266-48d6-9a24-3756727d59da.png)




