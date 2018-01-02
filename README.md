# opencv
opencv tutorial for machine learning

## Setup a Jupyter Notebook on Ubuntu 16.04

Install Python 2.7 and Pip
```
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get -y install python2.7 python-pip python-dev
$ python --version
$ pip --version
```
Upgrade pip from 8.1.1 to 9.0.1
```
$ sudo -H pip install --upgrade pip
```
Install Ipython
```
$ sudo apt-get -y install ipython ipython-notebook
```
Install Jupyter
```
$ sudo -H pip install jupyter
```
Launch Jupyter Notebook
```
jupyter notebook
```

## Quick way to install OpenCV


## Install OpenCV from source
https://www.pyimagesearch.com/2016/10/24/ubuntu-16-04-how-to-install-opencv/
```
$ sudo apt-get update
$ sudo apt-get upgrade
$ sudo apt-get install build-essential cmake pkg-config

$ sudo apt-get install libjpeg8-dev libtiff5-dev libjasper-dev libpng12-dev
$ sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
$ sudo apt-get install libxvidcore-dev libx264-dev

$ sudo apt-get install libgtk-3-dev

$ sudo apt-get install libatlas-base-dev gfortran
$ sudo apt-get install python2.7-dev python3.5-dev
```
