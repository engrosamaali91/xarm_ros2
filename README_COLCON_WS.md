# MoveIt Tutorials Source Build

Follow the [MoveIt Source Build](https://moveit.ros.org/install-moveit2/source/) instructions to set up a colcon workspace with MoveIt from the source.

Open a command line to your colcon workspace:

    cd $COLCON_WS/src

Download the MoveIt Tutorials source code:

    git clone https://github.com/ros-planning/moveit2_tutorials.git
    vcs import < moveit2_tutorials/moveit2_tutorials.repos
    rosdep install -r --from-paths . --ignore-src --rosdistro rolling -y

Configure and build the workspace:

    cd $COLCON_WS
    colcon build --event-handlers desktop_notification- status- --cmake-args -DCMAKE_BUILD_TYPE=Release




Issue:

    I solved issue by adding suggested paramter in the log file 
    I also ignore robotique packagabuild by going into the package location 

    ```shell
    touch COLCON_IGNORE
    ```
    
