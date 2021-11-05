# ROS DOCKER HELPER

Use this repo to create a ros dev environment for Clion with visual interface, X server is linked

You need to do :

    sudo docker-compose build

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