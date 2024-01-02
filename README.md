# zzangdol_docker-orbslam2

Ready-to-use implementation of ORB SLAM 2 on ROS, with docker compose.

- Docs Created : 24.01.03
- Reference : https://github.com/HyeonJaeGil/orbslam2-ros
- Reference : https://github.com/raulmur/ORB_SLAM2

- Since orbslam has dependecies on opencv3.4 and ros-melodic, we need to use docker container with network-option: host to communicate with main nodes on the host environment.

## Run the container

- On (Start)

```bash
docker compose up -d
docker exec -it orbslam2-ros-container /bin/bash
```

- Off (Stop)

```bash
docker exec -it orbslam2-ros-container /bin/bash
```
## BELOW GUIDES FROM -  https://github.com/HyeonJaeGil/orbslam2-ros?tab=readme-ov-file
If you need more information, try this url

### Enable GUI inside a container (important!)

You should enable GUI inside a container in order to run Pangolin viewer. The most simple way is to share xhost between local and container.

```bash
xhost + local:docker
```

Inside the container, run following command...

```bash
$ rosrun orbslam-ros RGBD \
  /root/ORB_SLAM2/Vocabulary/ORBvoc.txt \
  /root/catkin_ws/src/orbslam-ros/param/realsense.yaml
```

For Mono or Stereo example, adjust yaml files (similar to original ORB SLAM2)
You should prepare external camera so that it can publish image topics.
