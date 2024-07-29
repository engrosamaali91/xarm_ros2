Export domain id if needed
```shell
export ROS_DOMAIN_ID=<domain_id>
```

#ScaN THE NETWORK 

```shell
sudo apt-get install arp-scan
sudo arp-scan --localnet
```
Ping 
```
ping 192.168.68.166
```

SSH
```
ssh -X ping 192.168.68.166
```


Launch movo in rviz 
```shell
ros2 launch movo_viz view_robot.launch.py 
```
ROS2 for ZED tutorials and example 
```shell
https://github.com/stereolabs/zed-ros2-examples
```
