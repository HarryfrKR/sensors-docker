FROM ros:humble-perception

ENV WS_DIR="/ros2_ws"
ENV ROS_DOMAIN_ID=42
ENV ROS_LOCALHOST_ONLY=0

WORKDIR ${WS_DIR}

SHELL ["/bin/bash", "-c"]

ARG DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
 && apt-get install -y \
    build-essential \
    cmake \
    git-all \
    software-properties-common \
 && rm -rf /var/lib/apt/lists/*

RUN apt-get update \
 && apt-get install -y \
    ros-${ROS_DISTRO}-librealsense2* \
    ros-${ROS_DISTRO}-realsense2-* \
 && rm -rf /var/lib/apt/lists/*

RUN apt-get update \
 && apt-get install -y \
    ros-humble-rmw-cyclonedds-cpp \
    ros-${ROS_DISTRO}-rviz2 \
 && rm -rf /var/lib/apt/lists/*

ARG DEBIAN_FRONTEND=dialog

RUN echo "source /opt/ros/humble/setup.bash" >> /root/.bashrc
