ARG DOCKER_BASE_IMAGE=miniconda
FROM $DOCKER_BASE_IMAGE
ARG ROS_DISTRO=kinetic
ARG NUM_OF_CORE_TO_BUILD=3


RUN rm /bin/sh && ln -s /bin/bash /bin/sh

#RUN . /root/miniconda/etc/profile.d/conda.sh && \
#    conda update -n base -c defaults conda && \
#    conda create --name pcl && \
#    conda activate pcl && \
#    conda config --prepend channels conda-forge && \
#    conda install -c conda-forge pcl 
#RUN echo ". /root/miniconda/etc/profile.d/conda.sh" >> ~/.bashrc && \
    # echo "export PATH=/root/miniconda/bin/:$PATH" >> ~/.bashrc && \
    # echo "source /root/miniconda/bin/activate pcl" >> ~/.bashrc
#    echo "conda activate pcl" >> ~/.bashrc

RUN cd /root && \
    git clone https://github.com/assimp/assimp.git && \
    cd /assimp && mkdir build && cd build && \
    cmake .. -G 'Unix Makefiles' && \
    make && make install
    cd /../port/PyAssimp && python setup.py install



##########################
# install pcl1.8.1-dev
#RUN apt-get update && apt-get -y install \
#      software-properties-common \
#      libwayland-client0 \
#      libset-scalar-perl \
#      libgl1-mesa-dev \
#      libxcursor-dev \
#      libxi-dev \
#      libxinerama-dev \
#      libxrandr-dev

#RUN apt-get -y install \
#      libflann-dev \
#      libflann1.8 \
#      libboost-all-dev \
#      libxt-dev \
#      libeigen3-dev \
#      libqhull* libqhull-dev \
      # message passing interface parallel computing
#      mpi-default-dev openmpi-bin openmpi-common 

# Build dependency-VTK      
#RUN cd /root && \
#    wget http://www.vtk.org/files/release/7.1/VTK-7.1.0.tar.gz && \
#    tar -xf VTK-7.1.0.tar.gz && \
#    cd VTK-7.1.0 && mkdir build && cd build && \

#    cmake .. && \
#    make -j $NUM_OF_CORE_TO_BUILD && \
#    make install

# PCL install
#RUN cd /root && \
#    wget https://github.com/PointCloudLibrary/pcl/archive/pcl-1.8.0.tar.gz && \
#    tar -xf pcl-1.8.0.tar.gz && \
#    cd pcl-pcl-1.8.0 && mkdir build && cd build && \
#    apt-get update && \
#    apt-get -y install libopenni-dev libopenni2-dev && \
#    cmake -DBUILD_GPU=ON .. && \
    # latest pcl.1.8.1 already fixed compile problem with CUDA 9.0, 9.1
#    make -j $NUM_OF_CORE_TO_BUILD && \
#    make install

#RUN cd /root && \
#    pip install 'cython==0.25.2' && \
#    git clone https://github.com/strawlab/python-pcl.git && \
#    cd python-pcl && \
#    python setup.py build && \
#    python setup.py install 

#RUN apt-get install libpcl-dev
