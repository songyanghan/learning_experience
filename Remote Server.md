# Remote Server

[TOC]

## Command
* `df -h `
    * the df command displays information about total space and available space on a file system
* `sudo apt-get install`
* `wget`
* `ssh -Y`
* `uptime` check system running time, users, load
* command line copy from local to server
* check ubuntu version `lsb_release -d`

## Deep Learning Environment
tutorial: <https://towardsdatascience.com/build-and-setup-your-own-deep-learning-server-from-scratch-e771dacaa252>

### CUDA
install: <https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1804&target_type=debnetwork>

* Check you have installed the right version `nvcc -V`
* Check out details about your video card `nvidia-smi`

### verify cuDNN install
1. copy the cuDNN sample to a writable path. `cp -r /usr/src/cudnn_samples_v7/ $HOME`
2. go to the writable path. `cd $HOME/cudnn_samples_v7/mnistCUDNN`
3. Compile the mnistCUDNN sample. `make clean && make`
4. Run the ministCUDNN sample. `./mnistCUDNN`
    1. if it is properly installed, you see `Test passed!`

### Anaconda
#### verify (any of the following)
  * Enter `conda list`. If Anaconda is installed and working, this will display a list of installed packages and their versions.
  * Enter the command `python`. This command runs the Python shell. If Anaconda is installed and working, the version information it displays when it starts up will include “Anaconda”. To exit the Python shell, enter the command `quit()`.
  * Open Anaconda Navigator with the command `anaconda-navigator`. If Anaconda is installed properly, Anaconda Navigator will open.

#### install

1. Go to [Anaconda Repository](https://repo.continuum.io/archive/), find the installation for your OS and copy the address 
2. `wget {paste}`. Ex: [https://repo.continuum.io/archive/Anaconda3-5.2.0-Linux-x86_64.sh](https://repo.continuum.io/archive/Anaconda3-5.2.0-Linux-x86_64.sh)
3. Execute with: bash. Ex: `bash Anaconda3-5.2.0-Linux-x86_64.sh`

### Tensorflow
install: <https://www.tensorflow.org/install/pip>

#### Verify
`python -c 'import tensorflow as tf; print(tf.__version__)'  # for Python 2
python3 -c 'import tensorflow as tf; print(tf.__version__)'  # for Python 3`

### Remote Jupyter Lab
1. on server: `jupyter-lab --no-browser`
2. on laptop: `ssh -NL 8888:localhost:8888 <username>@<serverIP>`


## Analyze Disk Drives

Command | Description 
----|---
[df](https://wiki.base22.com/btg/unix-and-linux-df-command-33096359.html) | summarize free space on disk drive 
du | show disk space used by files or directories 

## Analyze CPU Utilization

Command | Description 
---|---
[top or topas](https://wiki.base22.com/btg/unix-and-linux-top-or-topas-command-33096374.html)| provides a rolling display of top cpu using processes. You need to just press q (small letter q) to quit or exit from top session.   


## Navigate the File System

Command | Description 
---|---
cd d | Change to directory d 
ls   | list the contents of the current directory   
ls -la   | list all contents of the directory in long format   
ls -latr   | list all contents of the directory in long format with the latest modified files last (handy to show the latest modified files at the bottom of the list where the prompt awaits your next command).   
pwd | See what directory you are currently in; this writes the absolute pathname of the current working directory to the standard output 
