# Caffe Installation



## Requirements

Python=3.6

Scikit-image==0.14.2



## Reference

https://mc.ai/installing-caffe-on-ubuntu-18-04-with-cuda-and-cudnn/



**Step 1: Install these packages and other dependencies**

```
# Install open-cv3
sudo apt install python3-opencv
sudo apt-get install libatlas-base-dev
sudo apt-get install libprotobuf-dev libleveldb-dev libsnappy-dev libopencv-dev libhdf5-serial-dev protobuf-compiler
sudo apt-get install libgflags-dev libgoogle-glog-dev liblmdb-dev
sudo pip3 install protobuf
sudo apt-get install --no-install-recommends libboost-all-dev
# Install Python3
sudo apt-get install the python3-dev

```

**Step 2: Go into caffee folder and modify the config file before compling**

```
cd caffe
```

**Step 3: Setup python library**

```
PYTHON_LIBRARIES := boost_python3 python3.6m
PYTHON_INCLUDE := /usr/include/python3.6m \
/usr/lib/python3.6/dist-packages/numpy/core/include
```

**Step 4: Compile**

```
make all -j8 # 4 represents number of CPU Cores
make pycaffe -j8 # 4 represents number of CPU Cores
make clean
export PYTHONPATH=~/caffe/python:$PYTHONPATH
```

**Testing**

```
python3
import caffe 
```



**Problems:** 

```
pip install -U scikit-image
```

If you have any problem, visit the reference website https://mc.ai/installing-caffe-on-ubuntu-18-04-with-cuda-and-cudnn/



## WORK WITH VIRTUAL ENVIRONMENT

Activate the virtual environment

```
workon your_environment
```

Take a look file `Makefile.config`

Modify the config file `Makefile.config`

```
PYTHON_LIBRARIES := boost_python3 python3.6m
PYTHON_INCLUDE := /home/hunglv/.virtualenvs/hand_pose/include/python3.6m \
                /home/hunglv/.virtualenvs/hand_pose/lib/python3.6/site-packages/numpy/core/include
```

