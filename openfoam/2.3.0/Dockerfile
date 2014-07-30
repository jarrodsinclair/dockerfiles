FROM ubuntu:13.10

# core updates
RUN apt-get -q update
RUN apt-get -q -y install build-essential software-properties-common adduser

# add ubuntu user
RUN adduser --disabled-password --gecos "" ubuntu

# install shell utilities
RUN apt-get -q -y install vim zip unzip curl
RUN apt-get -q -y install imagemagick ffmpeg

# install Python 2.7 and useful packages
RUN apt-get -q -y install python python-dev python-virtualenv python-pip
RUN apt-get -q -y install libfreetype6-dev libpng12-dev
RUN apt-get -q -y install libatlas-base-dev gfortran
RUN pip install numpy matplotlib scipy

# install OpenFOAM 2.3.0 (with system operations enabled)
RUN sh -c "echo deb http://www.openfoam.org/download/ubuntu $(lsb_release -cs) main > /etc/apt/sources.list.d/openfoam.list"
RUN apt-get -q update
RUN apt-get -q -y --force-yes install openfoam230
RUN apt-get -q -y --force-yes install paraviewopenfoam410
RUN sed -i "s/^[ \t][ \t]*allowSystemOperations[ \t][ \t]*0;/    allowSystemOperations   1;/g" /opt/openfoam230/etc/controlDict
USER ubuntu
RUN echo "" >> /home/ubuntu/.profile
RUN echo ". /opt/openfoam230/etc/bashrc" >> /home/ubuntu/.profile
RUN echo "" >> /home/ubuntu/.profile
USER root

# check installation in user shell
RUN su - -c "icoFoam -help" ubuntu

