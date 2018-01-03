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
Reproduce the result from: 
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
Download the package
```
$ wget https://github.com/opencv/opencv/archive/3.4.0.zip
$ unzip 3.4.0.zip

$ wget -O opencv_contrib.zip https://github.com/Itseez/opencv_contrib/archive/3.4.0.zip
$ unzip opencv_contrib.zip
```
Setup Python environment
```
$ cd ~
$ wget https://bootstrap.pypa.io/get-pip.py
$ sudo python get-pip.py
$ sudo -H pip install virtualenv virtualenvwrapper
$ sudo rm -rf ~/get-pip.py ~/.cache/pip
```
Add the following lines to ./bashrc 
```
# virtualenv and virtualenvwrapper
export WORKON_HOME=$HOME/.virtualenvs
source /usr/local/bin/virtualenvwrapper.sh
```
Open a new terminal
```
$ source ~/.bashrc
```
Create your own environment
```
$ mkvirtualenv cv -p python2
```
Open a new terminal, work on your new environment 
```
$ workon cv
$ pip install numpy
$ cd ~/opencv-3.4.0/
$ mkdir build
$ cd build
$ cmake -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/usr/local \
    -D INSTALL_PYTHON_EXAMPLES=ON \
    -D INSTALL_C_EXAMPLES=ON \
    -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib-3.4.0/modules \
    -D PYTHON_EXECUTABLE=~/.virtualenvs/cv/bin/python \
    -D BUILD_EXAMPLES=ON ..
```
I have 8 core CPU machine, so I can use
```
$ make -j8
```
Install and setup
```
$ sudo make install
$ sudo ldconfig
$ ls -l /usr/local/lib/python2.7/site-packages/
$ cd ~/.virtualenvs/cv/lib/python2.7/site-packages/
$ ln -s /usr/local/lib/python2.7/site-packages/cv2.so cv2.so
```
Test new installation in new terminal
```

(cv) ct@ct-PowerEdge-R310:~$ python
Python 2.7.12 (default, Nov 20 2017, 18:23:56) 
[GCC 5.4.0 20160609] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>> import cv2
>>> cv2.__version__
'3.4.0'
>>> 

```
Finally, remove the opencv source file and zip files as needed.
