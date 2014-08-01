FROM ubuntu:13.10

RUN apt-get -q update && \
    apt-get -q -y upgrade && \
    apt-get -q -y install build-essential software-properties-common adduser && \
    apt-get -q -y install vim zip unzip curl wget imagemagick ffmpeg && \
    apt-get -q -y install python python3 python-dev python3-dev && \
    wget -nv https://bootstrap.pypa.io/get-pip.py && \
    python2 get-pip.py && python3 get-pip.py && rm -rf get-pip.py && \
    apt-get -q -y install libfreetype6-dev libpng12-dev libatlas-base-dev gfortran && \
    apt-get -q -y install libtiff4-dev libjpeg8-dev zlib1g-dev liblcms2-dev libwebp-dev && \
    pip2 -q install numpy matplotlib scipy Pillow && \
    pip3 -q install numpy matplotlib scipy Pillow && \
    sh -c "echo deb http://www.openfoam.org/download/ubuntu $(lsb_release -cs) main > /etc/apt/sources.list.d/openfoam.list" && \
    apt-get -q update && \
    apt-get -q -y --force-yes install openfoam230 && \
    apt-get -q -y --force-yes install paraviewopenfoam410 && \
    sed -i "s/^[ \t][ \t]*allowSystemOperations[ \t][ \t]*0;/    allowSystemOperations   1;/g" /opt/openfoam230/etc/controlDict && \
    adduser --disabled-password --gecos "" ubuntu && \
    su - -c "printf '\n. /opt/openfoam230/etc/bashrc\n\n' >> .profile" ubuntu