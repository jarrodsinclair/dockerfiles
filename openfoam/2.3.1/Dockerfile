FROM jarrodsinclair/paraview_4.2.0_osmesa
MAINTAINER Jarrod Sinclair <jarrod.sinclair@gmail.com>

RUN apt-get -q update && \
    apt-get -q -y upgrade && \
    apt-get -q -y install adduser vim zip unzip imagemagick libav-tools python3 python3-dev && \
    curl -s https://bootstrap.pypa.io/get-pip.py | python3 && \

    pip2 -q install numpy && pip3 -q install numpy && \
    apt-get -q -y install libatlas-base-dev gfortran && \
    pip2 -q install scipy && pip3 -q install scipy && \
    apt-get -q -y install libfreetype6-dev libxft-dev && \
    pip2 -q install matplotlib && pip3 -q install matplotlib && \
    apt-get -q -y install libjpeg-dev libtiff-dev liblcms2-dev libwebp-dev && \
    pip2 -q install Pillow && pip3 -q install Pillow && \

    echo "deb http://www.openfoam.org/download/ubuntu utopic main" > /etc/apt/sources.list.d/openfoam.list && \
    apt-get -q update && \
    apt-get -q -y --force-yes install openfoam231 && \
    adduser --disabled-password --gecos "" ubuntu

USER ubuntu

WORKDIR /home/ubuntu

ENV USER ubuntu
ENV LOGNAME ubuntu
ENV HOME /home/ubuntu
ENV PWD /home/ubuntu
ENV SHELL /bin/bash
ENV PATH /opt/ThirdParty-2.3.1/platforms/linux64Gcc/gperftools-svn/bin:/home/ubuntu/OpenFOAM/ubuntu-2.3.1/platforms/linux64GccDPOpt/bin:/opt/site/2.3.1/platforms/linux64GccDPOpt/bin:/opt/openfoam231/platforms/linux64GccDPOpt/bin:/opt/openfoam231/bin:/opt/openfoam231/wmake:/usr/local/bin:/usr/bin:/bin:/usr/local/sbin:/usr/sbin:/sbin
ENV LD_LIBRARY_PATH /opt/ThirdParty-2.3.1/platforms/linux64Gcc/gperftools-svn/lib:/opt/openfoam231/platforms/linux64GccDPOpt/lib/openmpi-system:/opt/ThirdParty-2.3.1/platforms/linux64GccDPOpt/lib/openmpi-system:/usr/lib/openmpi/lib:/home/ubuntu/OpenFOAM/ubuntu-2.3.1/platforms/linux64GccDPOpt/lib:/opt/site/2.3.1/platforms/linux64GccDPOpt/lib:/opt/openfoam231/platforms/linux64GccDPOpt/lib:/opt/ThirdParty-2.3.1/platforms/linux64GccDPOpt/lib:/opt/openfoam231/platforms/linux64GccDPOpt/lib/dummy
ENV BOOST_ARCH_PATH /opt/ThirdParty-2.3.1/platforms/linux64Gcc/boost-system
ENV CGAL_ARCH_PATH /opt/ThirdParty-2.3.1/platforms/linux64Gcc/CGAL-4.3
ENV FOAM_APP /opt/openfoam231/applications
ENV FOAM_APPBIN /opt/openfoam231/platforms/linux64GccDPOpt/bin
ENV FOAM_EXT_LIBBIN /opt/ThirdParty-2.3.1/platforms/linux64GccDPOpt/lib
ENV FOAM_INST_DIR /opt
ENV FOAM_JOB_DIR /opt/jobControl
ENV FOAM_LIBBIN /opt/openfoam231/platforms/linux64GccDPOpt/lib
ENV FOAM_MPI openmpi-system
ENV FOAM_RUN /home/ubuntu/OpenFOAM/ubuntu-2.3.1/run
ENV FOAM_SITE_APPBIN /opt/site/2.3.1/platforms/linux64GccDPOpt/bin
ENV FOAM_SITE_LIBBIN /opt/site/2.3.1/platforms/linux64GccDPOpt/lib
ENV FOAM_SOLVERS /opt/openfoam231/applications/solvers
ENV FOAM_SRC /opt/openfoam231/src
ENV FOAM_TUTORIALS /opt/openfoam231/tutorials
ENV FOAM_USER_APPBIN /home/ubuntu/OpenFOAM/ubuntu-2.3.1/platforms/linux64GccDPOpt/bin
ENV FOAM_USER_LIBBIN /home/ubuntu/OpenFOAM/ubuntu-2.3.1/platforms/linux64GccDPOpt/lib
ENV FOAM_UTILITIES /opt/openfoam231/applications/utilities
ENV MPI_ARCH_PATH /usr/lib/openmpi
ENV MPI_BUFFER_SIZE 20000000
ENV WM_ARCH linux64
ENV WM_ARCH_OPTION 64
ENV WM_CC gcc
ENV WM_CFLAGS -m64 -fPIC
ENV WM_COMPILER Gcc
ENV WM_COMPILER_LIB_ARCH 64
ENV WM_COMPILE_OPTION Opt
ENV WM_CXX g++
ENV WM_CXXFLAGS -m64 -fPIC
ENV WM_DIR /opt/openfoam231/wmake
ENV WM_LDFLAGS -m64
ENV WM_LINK_LANGUAGE c++
ENV WM_MPLIB SYSTEMOPENMPI
ENV WM_OPTIONS linux64GccDPOpt
ENV WM_OSTYPE POSIX
ENV WM_PRECISION_OPTION DP
ENV WM_PROJECT OpenFOAM
ENV WM_PROJECT_DIR /opt/openfoam231
ENV WM_PROJECT_INST_DIR /opt
ENV WM_PROJECT_USER_DIR /home/ubuntu/OpenFOAM/ubuntu-2.3.1
ENV WM_PROJECT_VERSION 2.3.1
ENV WM_THIRD_PARTY_DIR /opt/ThirdParty-2.3.1

