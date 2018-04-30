# <b>Soccer On Your Tabletop</b> [[Project Page]](http://grail.cs.washington.edu/projects/soccer/)

[Konstantinos Rematas](https://homes.cs.washington.edu/~krematas/), [Ira Kemelmacher-Shlizerman](https://homes.cs.washington.edu/~kemelmi/), [Brian Curless](https://homes.cs.washington.edu/~curless/), [Steve Seitz](https://homes.cs.washington.edu/~seitz/), in CVPR 2018

![Teaser Image](http://grail.cs.washington.edu/projects/soccer/images/teaser.png)


Warning: I am in the process of transferring the repo, so many things will probably not work.

-----------------

### Overview ###
This repository contains:

Upconversion of YouTube Soccer videos to 3D
  - Camera Calibration
  - Player Analysis (detection/segmentation/tracking)
  - Player Depth estimation
  - Temporal Game Reconstruction

Scripts for getting training data from video games
  - Electronic Arts FIFA 2016 RenderDoc Depth buffer capture
  - Depth buffer to point cloud

Visualization tools
  - Example Unity project
  - Hololens VS Solution

### Dependencies ###
These are the non "pip3 install" dependencies:
- [Detectron](https://github.com/facebookresearch/Detectron) for detection and (instance) segmentation.
- [OpenPose](https://github.com/CMU-Perceptual-Computing-Lab/openpose) for the players' pose estimation.
- [OpenCV 3.1](https://github.com/opencv/opencv) + [OpenCV_contrib](https://github.com/opencv/opencv_contrib) for image loading/edge estimation etc. I followed [this](https://www.pyimagesearch.com/2015/07/20/install-opencv-3-0-and-python-3-4-on-ubuntu/) guide and it worked fine.
- [Eigen3](http://eigen.tuxfamily.org/index.php?title=Main_Page) for the instance segmentation
- Boost
- CMake


-----------------

## Upconversion of YouTube Soccer videos to 3D ##
The pipeline contains parts written or depending on python2, python3, C/C++, which makes it a bit difficult to combine everything in one entity. Therefore we break the pipeline into individual parts that have specific inputs and outputs (eg png to pickle) and communicate through a python3 class that reads and writes intermediate results.  
