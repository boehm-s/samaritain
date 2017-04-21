## Goal of the project

The goal of this project is to detect dangerous behaviour from video feeds, like fire, guns...
To do this we are using the darknet library.

## Prerequistes

You have two choices to compile this program:

1. with CUDA
  The program will run faster (16gb ram / gtx 960 2gb => 15fps)

2. without CUDA
  The program will run slower (16gb ram / gtx 960 2gb => < 1fps)

so we advise you to  install CUDA (we are using cuda 8.0)
##### To install cuda :
[Linux](https://doc.ubuntu-fr.org/cuda)
[Windows](https://developer.nvidia.com/cuda-downloads)

##### To install opencv2 :
`In both cases (CUDA || !CUDA) you will need to install opencv`
we are using opencv2 so to install it :

[Linux](https://doc.ubuntu-fr.org/opencv)
[Mac](https://jjyap.wordpress.com/2014/05/24/installing-opencv-2-4-9-on-mac-osx-with-python-support/)
[Windows](http://docs.opencv.org/2.4/doc/tutorials/introduction/windows_install/windows_install.html)

---

## Compile

You now have the required programs to run `samaritain`
To compile our program, you first need to compile the darknet static library, to do so:
- go to the `darknet` folder
- edit the `Makefile`
- set GPU, CUDNN and OPENCV to 1 (only OPENCV if you don't use CUDA)
- run the Makefile
- copy the darknet.a to app/lib/libdarknet.a
- go to the app folder
- run get_weights.sh script
- run the Makefile
- execute the program

So now in command line :
``` shell
cd darknet
emacs -nw Makefile
    GPU=1
    CUDNN=1
    OPENCV=1
    DEBUG=0

make
cp darknet.a ../app/lib/libdarknet.a
cd ../app
cd weights
./get_weights.sh
cd ..
make
./samaritain detector demo cfg/coco.data cfg/yolo.cfg weights/yolo.weights
```
