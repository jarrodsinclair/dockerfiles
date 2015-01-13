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

ENV USER="ubuntu" \
    LOGNAME="ubuntu" \
    HOME="/home/ubuntu" \
    PWD="/home/ubuntu" \
    SHELL="/bin/bash" \
    PATH="/opt/ThirdParty-2.3.1/platforms/linux64Gcc/gperftools-svn/bin:/home/ubuntu/OpenFOAM/ubuntu-2.3.1/platforms/linux64GccDPOpt/bin:/opt/site/2.3.1/platforms/linux64GccDPOpt/bin:/opt/openfoam231/platforms/linux64GccDPOpt/bin:/opt/openfoam231/bin:/opt/openfoam231/wmake:/usr/local/bin:/usr/bin:/bin" \
    LD_LIBRARY_PATH="/opt/ThirdParty-2.3.1/platforms/linux64Gcc/gperftools-svn/lib:/opt/openfoam231/platforms/linux64GccDPOpt/lib/openmpi-system:/opt/ThirdParty-2.3.1/platforms/linux64GccDPOpt/lib/openmpi-system:/usr/lib/openmpi/lib:/home/ubuntu/OpenFOAM/ubuntu-2.3.1/platforms/linux64GccDPOpt/lib:/opt/site/2.3.1/platforms/linux64GccDPOpt/lib:/opt/openfoam231/platforms/linux64GccDPOpt/lib:/opt/ThirdParty-2.3.1/platforms/linux64GccDPOpt/lib:/opt/openfoam231/platforms/linux64GccDPOpt/lib/dummy" \
    BOOST_ARCH_PATH="/opt/ThirdParty-2.3.1/platforms/linux64Gcc/boost-system" \
    CGAL_ARCH_PATH="/opt/ThirdParty-2.3.1/platforms/linux64Gcc/CGAL-4.3" \
    FOAM_APP="/opt/openfoam231/applications" \
    FOAM_APPBIN="/opt/openfoam231/platforms/linux64GccDPOpt/bin" \
    FOAM_EXT_LIBBIN="/opt/ThirdParty-2.3.1/platforms/linux64GccDPOpt/lib" \
    FOAM_INST_DIR="/opt" \
    FOAM_JOB_DIR="/opt/jobControl" \
    FOAM_LIBBIN="/opt/openfoam231/platforms/linux64GccDPOpt/lib" \
    FOAM_MPI="openmpi-system" \
    FOAM_RUN="/home/ubuntu/OpenFOAM/ubuntu-2.3.1/run" \
    FOAM_SITE_APPBIN="/opt/site/2.3.1/platforms/linux64GccDPOpt/bin" \
    FOAM_SITE_LIBBIN="/opt/site/2.3.1/platforms/linux64GccDPOpt/lib" \
    FOAM_SOLVERS="/opt/openfoam231/applications/solvers" \
    FOAM_SRC="/opt/openfoam231/src" \
    FOAM_TUTORIALS="/opt/openfoam231/tutorials" \
    FOAM_USER_APPBIN="/home/ubuntu/OpenFOAM/ubuntu-2.3.1/platforms/linux64GccDPOpt/bin" \
    FOAM_USER_LIBBIN="/home/ubuntu/OpenFOAM/ubuntu-2.3.1/platforms/linux64GccDPOpt/lib" \
    FOAM_UTILITIES="/opt/openfoam231/applications/utilities" \
    MPI_ARCH_PATH="/usr/lib/openmpi" \
    MPI_BUFFER_SIZE="20000000" \
    WM_ARCH="linux64" \
    WM_ARCH_OPTION="64" \
    WM_CC="gcc" \
    WM_CFLAGS="-m64 -fPIC" \
    WM_COMPILER="Gcc" \
    WM_COMPILER_LIB_ARCH="64" \
    WM_COMPILE_OPTION="Opt" \
    WM_CXX="g++" \
    WM_CXXFLAGS="-m64 -fPIC" \
    WM_DIR="/opt/openfoam231/wmake" \
    WM_LDFLAGS="-m64" \
    WM_LINK_LANGUAGE="c++" \
    WM_MPLIB="SYSTEMOPENMPI" \
    WM_OPTIONS="linux64GccDPOpt" \
    WM_OSTYPE="POSIX" \
    WM_PRECISION_OPTION="DP" \
    WM_PROJECT="OpenFOAM" \
    WM_PROJECT_DIR="/opt/openfoam231" \
    WM_PROJECT_INST_DIR="/opt" \
    WM_PROJECT_USER_DIR="/home/ubuntu/OpenFOAM/ubuntu-2.3.1" \
    WM_PROJECT_VERSION="2.3.1" \
    WM_THIRD_PARTY_DIR="/opt/ThirdParty-2.3.1"

