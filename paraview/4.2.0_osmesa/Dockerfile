FROM ubuntu:14.10
MAINTAINER Jarrod Sinclair <jarrod.sinclair@gmail.com>

RUN apt-get -q update && \
    apt-get -q -y upgrade && \
    apt-get -q -y install build-essential software-properties-common && \
    apt-get -q -y install curl wget git python python-dev && \
    curl -s https://bootstrap.pypa.io/get-pip.py | python2 && \

    mkdir -p /root/build && cd /root/build && \
    apt-get -q -y install cmake libosmesa6-dev libglu1-mesa-dev && \
    git clone https://github.com/Kitware/ParaView.git pv-git && cd pv-git && \
    git config submodule.VTK.url https://github.com/Kitware/VTK.git && \
    git checkout v4.2.0 && git submodule init && git submodule update && \

    mkdir -p /root/build/pv-bin && cd /root/build/pv-bin && \
    cmake \
        -D CMAKE_BUILD_TYPE=Release \
        -D BUILD_TESTING:BOOL=OFF \
        -D PARAVIEW_BUILD_QT_GUI:BOOL=OFF \
        -D PARAVIEW_ENABLE_PYTHON:BOOL=ON \
        -D PARAVIEW_INSTALL_DEVELOPMENT_FILES:BOOL=OFF \
        -D OPENGL_INCLUDE_DIR=/usr/include \
        -D OPENGL_gl_LIBRARY="" \
        -D OPENGL_glu_LIBRARY=/usr/lib/x86_64-linux-gnu/libGLU.so \
        -D VTK_USE_X:BOOL=OFF \
        -D VTK_OPENGL_HAS_OSMESA:BOOL=ON \
        -D OSMESA_INCLUDE_DIR=/usr/include \
        -D OSMESA_LIBRARY=/usr/lib/x86_64-linux-gnu/libOSMesa.so \
        ../pv-git && \
    make -j4 && make install && \
    cd / && rm -rf /root/build
