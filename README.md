# rknn-single-thread-3566
RKNN single thread for Orange Pi 3B

The code is copied somewhere and modified to use on Orange Pi 3B since this board has only single thread.

Depend on your Python version, you need to download the RKNN Toolkit Lite 2 from this https://github.com/rockchip-linux/rknn-toolkit2
Included in this github is the wheel version 1.5.0 for Python 3.9. Install it by typing command

` pip install rknn_toolkit_lite2-1.5.0-cp39-cp39-linux_aarch64.whl `

The model `yolov5s.rknn` is converted from `yolov5s.onnx` using rknn_toolkit_lite2-1.5.0, maybe 1.5.2 works.

Maybe you also need to copy the file ` librknnrt.so ` to /usr/lib too, and install opencv module

` pip install opencv-python `

Check your Camera used in /dev/video0 or /dev/video1, and edit the code in main.py to the corresponance camera

` cap = cv2.VideoCapture(0) `

then run testing with images and dataset included

`python deploy.py`

if everthing run well, run the camera

`python cameera.py`

The rkcat.sh can be running with 

` sudo bash rkcat.sh ` 

to check the NPU performance

Here is demo i run on Orange Pi 3B with USB Camera, it can reach 20fps

![orangepi3b-rknn](https://github.com/thanhtantran/rknn-single-thread-3566/assets/5319910/b2f298a4-def8-420e-a7f6-5869a86e489b)


## Acknowledgements
- https://github.com/ultralytics/yolov5
- https://github.com/rockchip-linux/rknn-toolkit2
- https://github.com/airockchip/rknn_model_zoo
- https://github.com/leafqycc/rknn-multi-threaded
