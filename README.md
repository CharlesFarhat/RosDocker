# ROS DOCKER HELPER

Use this repo to create a ros dev environment for Clion with visual interface, X server is linked

You need to do :

    sudo docker-compose build

Install nvidia docker passtrhought (this is a workaround for ubuntu 21.04) :

    distribution='ubuntu20.04' \
   && curl -s -L https://nvidia.github.io/nvidia-docker/gpgkey | sudo apt-key add - \
   && curl -s -L https://nvidia.github.io/nvidia-docker/$distribution/nvidia-docker.list | sudo tee /etc/apt/sources.list.d/nvidia-docker.list

   sudo apt-get update
   sudo apt-get install -y nvidia-docker2
   sudo systemctl restart docker

then :
    sudo docker-compose up -d

Then you need to allow X server com from outsite :

    xhost +local:docker


### To connect use :

    sudo docker exec -it ros /bin/bash

ssh is only used for Clion acess,

follow this guide to configure :
    https://www.allaban.me/posts/2020/08/ros2-setup-ide-docker/

Please note that clion will upload you project folder to execute it in the container, be carefull when using large files... (add exclude directory for clion)
