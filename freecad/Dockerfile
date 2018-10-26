ARG DOCKER_BASE_IMAGE=ros-docker-base
FROM $DOCKER_BASE_IMAGE
ARG ROS_DISTRO=kinetic

RUN apt-get install -y software-properties-common python-software-properties && \
    add-apt-repository ppa:freecad-maintainers/freecad-stable && \
    apt-get update 
RUN apt-get install -y freecad freecad-doc 
