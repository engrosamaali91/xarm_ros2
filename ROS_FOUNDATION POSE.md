# Set Up Development Environment

Step 1

```shell
mkdir -p ~/ISAAC_ROS_WS/src && cd ~/ISAAC_ROS_WS/src

```
Step 2
```shell
echo "export ISAAC_ROS_WS=${HOME}/workspaces/isaac_ros-dev/" >> ~/.bashrc
source ~/.bashrc
```
Step 3

```shell
git clone https://github.com/NVIDIA-ISAAC-ROS/isaac_ros_common.git
```

# Download Quickstart assets
Make sure required libraries are installed.
```shell
sudo apt-get install -y curl tar
```
Then, run these commands to download the asset from NGC.

```shell
NGC_ORG="nvidia"
NGC_TEAM="isaac"
NGC_RESOURCE="isaac_ros_assets"
NGC_VERSION="isaac_ros_centerpose"
NGC_FILENAME="quickstart.tar.gz"

REQ_URL="https://api.ngc.nvidia.com/v2/resources/$NGC_ORG/$NGC_TEAM/$NGC_RESOURCE/versions/$NGC_VERSION/files/$NGC_FILENAME"

mkdir -p ${ISAAC_ROS_WS}/isaac_ros_assets/${NGC_VERSION} && \
    curl -LO --request GET "${REQ_URL}" && \
    tar -xf ${NGC_FILENAME} -C ${ISAAC_ROS_WS}/isaac_ros_assets/${NGC_VERSION} && \
    rm ${NGC_FILENAME}
```
Download the CenterPose shoe ONNX file to the models repository directory with version 1:

```shell
mkdir -p ${ISAAC_ROS_WS}/isaac_ros_assets/models/centerpose_shoe/1 && \
  cd ${ISAAC_ROS_WS}/isaac_ros_assets/models/centerpose_shoe/1 && \
  wget --content-disposition 'https://api.ngc.nvidia.com/v2/models/org/nvidia/team/tao/centerpose/deployable_dla34/files?redirect=true&path=shoe_DLA34.onnx' -O model.onnx
```
Move the quickstart model configuration file to the model repository.

```
cp ${ISAAC_ROS_WS}/isaac_ros_assets/isaac_ros_centerpose/config.pbtxt ${ISAAC_ROS_WS}/isaac_ros_assets/models/centerpose_shoe/config.pbtxt
```
