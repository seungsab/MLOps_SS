## 1. Let's Check GPU Device!
Simply run this code in your command line (for me, Git Bash in WINDOWS)
```bash
nvidia-smi --query-gpu=gpu_name --format=csv
```
> Output
```bash
user@DESKTOP-9CD5Q7P MINGW64 ~/Desktop/Useful_tutorials (main)
$ nvidia-smi --query-gpu=gpu_name --format=csv
name
NVIDIA GeForce RTX 2080 with Max-Q Design
```

## **[2. How to Check CUDA Version Easily](https://varhowto.com/check-pytorch-cuda-version/)**

#### **1. Method 1 — Use `nvcc` to check CUDA version for PyTorch**
To use nvcc to check CUDA version, run
```bash
nvcc --version
```
> Example of Output (Cuda V11.0)
```bash
$ nvcc --version
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2020 NVIDIA Corporation
Built on Wed_Jul_22_19:09:35_Pacific_Daylight_Time_2020
Cuda compilation tools, release 11.0, V11.0.221
Build cuda_11.0_bu.relgpu_drvr445TC445_37.28845127_0
```

#### **2. Method 2 — Use `nvcc` to check CUDA version for PyTorch**
To use nvidia-smi to check CUDA version, directly run
```bash
nvidia-smi
```
> Example of Output (Cuda V11.0)
```bash
user@DESKTOP-9CD5Q7P MINGW64 ~/Desktop/Useful_tutorials (main)
$ nvidia-smi
Sat Aug 12 12:18:13 2023
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 511.65       Driver Version: 511.65       CUDA Version: 11.6     |
|-------------------------------+----------------------+----------------------+
| GPU  Name            TCC/WDDM | Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|                               |                      |               MIG M. |
|===============================+======================+======================|
|   0  NVIDIA GeForce ... WDDM  | 00000000:01:00.0  On |                  N/A |
| N/A   55C    P8    18W /  N/A |   1447MiB /  8192MiB |     12%      Default |
|                               |                      |                  N/A |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                                  |
|  GPU   GI   CI        PID   Type   Process name                  GPU Memory |
|        ID   ID                                                   Usage      |
|=============================================================================|
|    0   N/A  N/A      1524    C+G                                   N/A      |
|    0   N/A  N/A     21552    C+G   ...5n1h2txyewy\SearchApp.exe    N/A      |
|    0   N/A  N/A     24524    C+G   C:\Windows\explorer.exe         N/A      |
|    0   N/A  N/A     25796    C+G   ...artMenuExperienceHost.exe    N/A      |
|    0   N/A  N/A     26216    C+G   ...5n1h2txyewy\SearchApp.exe    N/A      |
|    0   N/A  N/A     27616    C+G   ...ge\Application\msedge.exe    N/A      |
|    0   N/A  N/A     27900    C+G   ...e\PhoneExperienceHost.exe    N/A      |
|    0   N/A  N/A     28080    C+G   ...me\Application\chrome.exe    N/A      |
|    0   N/A  N/A     28740    C+G   ...3d8bbwe\CalculatorApp.exe    N/A      |
|    0   N/A  N/A     29212    C+G   ...2txyewy\TextInputHost.exe    N/A      |
|    0   N/A  N/A     29644    C+G   ...oft\OneDrive\OneDrive.exe    N/A      |
|    0   N/A  N/A     30108    C+G   ...8wekyb3d8bbwe\Cortana.exe    N/A      |
|    0   N/A  N/A     31776    C+G   ...8bbwe\WindowsTerminal.exe    N/A      |
|    0   N/A  N/A     31968    C+G   ...y\ShellExperienceHost.exe    N/A      |
|    0   N/A  N/A     32388    C+G   ...icrosoft VS Code\Code.exe    N/A      |
|    0   N/A  N/A     32892    C+G   ...bbwe\Microsoft.Photos.exe    N/A      |
+-----------------------------------------------------------------------------+
```

> **The versions of CUDA are different in nvcc and nvidia-smi**

- If Different CUDA versions are shown by nvcc and nvidia-smi it’s not necessarily a problem and maybe not even installed.
nvidia-smi pertains to the GPU Driver and includes the CUDA Driver API version not the actual CUDA runtime version.
- **If you want to use CUDE for DL libraries (PyTorch, Tensorflow, and so on), you should use the version of CUDA from `nvcc -version`**
- For my setting, versions of DL libraries should be chosned based on CUDA V11.0.221

FYI, please check the following blogs for more information.
- [nvcc-V와 nvidia-smi CUDA버전이 다를 때](https://kumoh-irl.tistory.com/91)
- [nvidia-smi와 nvcc로 본 CUDA version이 다를 때](https://bo-10000.tistory.com/73)
- [If Different CUDA versions are shown by nvcc and nvidia-smi ](https://medium.com/@brianhourigan/if-different-cuda-versions-are-shown-by-nvcc-and-nvidia-smi-its-necessarily-not-a-problem-and-311eda26856c)

## **[3. Compatibility between NVIDIA GPU and Dirvers with CUDA](https://kyumdoctor.tistory.com/68)**
All GPU device in NVIDIA has own compatibility to CUDA toolkits. Also, a certain CUDA toolkit is compatible to NVIDIA driver.

1. [GPU Device] Check your device of GPS (See Section #1).
2. [CUDA toolkit] Check compatible version of CUDA toolkit for your GPU from [CUDA GPUs](https://developer.nvidia.com/cuda-gpus) or [CUDA in WIKI](https://en.wikipedia.org/wiki/CUDA#GPUs_supported)
3. [NVIDIA Drivers for CUDA toolkit] Check required driver version from [Drivers & CUDA](https://docs.nvidia.com/cuda/cuda-toolkit-release-notes/index.html)
4. [CuDNN for DL Libraries] Check the list for DL library version with corresponding cuDNN & CUDA
- [Nvidia driver, CUDA, cuDNN, TensorFlow 버전 호환성 맞추기](https://robot9710.tistory.com/29)
- [For Tensorflow, check CUDA & cuDNN](https://www.tensorflow.org/install/source_windows#gpu)
- [For PyTorch, check CUDA & cuDNN](https://pytorch.org/get-started/previous-versions/)
5. [Install CUDA X.x] Install Cuda Toolkit for your GPU [Download CUDA-toolkit](https://developer.nvidia.com/cuda-toolkit-archive)
6. [Download Cudnn X.X] Download CuDNN for the version of Cuda toolkit [Download Cudnn](https://developer.nvidia.com/rdp/cudnn-archive) 
7. [Copy Cudnn folders to Cuda-toolkit folder] Copy `bin`, `include` and `lib` folder in Cudnn (you downloaded), then copy these folders to overwrite them to the directory of Cuda-toolkit folder.
8. [Add CUDA toolkit folder to Global Environment path] `System` - `Advanced Setting` - `Environment Variable` - `Path` in User variable - Add the following folders`
- C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\bin
- C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\include
- C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v11.8\lib
> Note) Root directory (`C:\Program Files\`) may be changed according to your installation. Then, just chamge this part to your own root.
9. [Check version of CUDA] Open window terminal, then enter "nvcc --version" in command line. If the output includes a right version of CUDA, then setting for CUDA-toolkit have been done!
10. Create a new virtual environment via python or anaconda:
```bash
conda create -n [name of VE] python=3.x
```
11. After creating VE, activate the new VE via the following line,
```bash
conda activate [name of VE]
``` 
12. Install DL libraries (torch or tensorflow) by checking compatible versions of DL libraries for your cuda-toolkit.
- [For Tensorflow](https://www.tensorflow.org/install/source_windows?hl=ko#gpu)
- [For Pytorch](https://pytorch.org/get-started/previous-versions/)
- [How to Choose Version (in Korean)](https://jjuke-brain.tistory.com/entry/GPU-%EC%84%9C%EB%B2%84-%EC%82%AC%EC%9A%A9%EB%B2%95-CUDA-PyTorch-%EB%B2%84%EC%A0%84-%EB%A7%9E%EC%B6%94%EA%B8%B0-%EC%B4%9D%EC%A0%95%EB%A6%AC)

[[Tensorflow] 텐서플로우 GPU 확인, 특정 GPU 사용 방법](https://jimmy-ai.tistory.com/121)

[Trouble Shooting #1] When error occurs during pip install
1) Download wheel files for PyTorch, TorchAudio, and etc.
- [Torch_stable_wheel](https://download.pytorch.org/whl/torch_stable.html)
Example:
```text
cu113/torch-1.12.0%2Bcu113-cp310-cp310-linux_x86_64.whl
```
- cu113: Cuda Version
- torch-1.12.0: PyTorch Version 1.12.0
- cp310: Python Version 3.10
- OS: linux_x86_64

2) Install Whl-file downloaded
- [How_to_Install_whl-file](https://www.delftstack.com/ko/howto/python/how-to-install-a-python-package-.whl-file/)


