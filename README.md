# Modeling-Environment-
## This is a list of commands that should be ran in order to set up the environment

### First download miniconda
```
wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh 
```
### Then change the permissions in order to run the installer
```
chmod +x Miniconda3-latest-Linux-x86_64.sh 
```
### Then run the installer
```
bash Miniconda3-latest-Linux-x86_64.sh 
```
### Then close out of any terminal you have open. If you are doing this over SSH then close the window. If local then restart computer. Then we will download the evironment file.
```
curl -OL https://raw.githubusercontent.com/cyneuro/Modeling-Environment-Setup/refs/heads/main/environment.yml
```
### Now we will create the conda environment
``` 
conda env create -f environment.yml
```
### Now you will be able to activate the anaconda environment using the command (NME stands for Neural Modeling Environment)
``` 
conda activate NME
``` 
### Some packages do not install using Conda, so we will use pip to finish the install process.

### This line is only needed if you plan on doing runs in parallel. You should have a version of mpi loaded before install for example mpich or openmpi. 
```
pip install mpi4py-mpich
```
``` 
pip install bmtk
```
### There is a pip install for BMTool but the install from GitHub works better
``` 
git clone https://github.com/cyneuro/bmtool.git
cd bmtool
python setup.py develop
``` 
### This should be a good starting point and have every package someone needs to get started with neural modeling. 
