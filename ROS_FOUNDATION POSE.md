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
