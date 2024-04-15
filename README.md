# Visual Computing Project with HUAWEI: High Performance Hand Pose Estimation
In this project, our task is to find a hand pose estimation model, deploy it to the HUAWEI Atlas 200 DK
board, and achieve a performance better than 20 fps for the whole pipeline, which includes
pre-processing, model execution, and post-processing.

### To run the 3D model HandPose X:
```python runhandx.py```

### To run the 2D model:
```python runsimple2d.py```

### The result of HandPose X model:
![handx result](https://github.com/Codylyp/High-Performance-Hand-Pose-Estimation/blob/main/handx_result.gif)

Considering the different methods, losses, and network architectures of the two models, we
infer that the HandPose X model has better predictions than the 2D Hand Pose Estimation
RGB model due to the following reasons:

### Analysis:
1. The HandPose X model predicts the coordinates of joints directly, which could avoid
the possible precision problem when extracting joints from heatmaps.


2. The HandPose X uses the Wing loss, which is proposed for keypoints detection of
human faces, and it could have a larger gradient when the error is small. It could work
better than the IOU loss of the 2D Hand Pose Estimation RGB model.


3. The network architecture of the 2D Hand Pose Estimation RGB model is too shallow,
which leads to its low accuracy.
