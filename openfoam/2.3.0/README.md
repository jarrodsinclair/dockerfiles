openfoam_2.3.0 Docker image
===========================

A Docker image bundling [OpenFOAM 2.3.0](http://openfoam.org/version2.3.0/) and useful utilities.

Image includes:

- Ubuntu 13.10 64-bit
- OpenFOAM 2.3.0
- ParaView 4.1.0 using OSMesa (pvpython, pvbatch, pvserver)
- Python 2.7 & 3.3
- pip (pip2 and pip3)
- NumPy, SciPy, Matplotlib, Pillow (latest versions at build time via pip2/pip3)
- ImageMagick, Libav
- Wget, cURL, git
- Zip, UnZip
- Vim

The OpenFOAM environment is configured for the "ubuntu" user via Dockerfile ENV statements, so an interactive login shell is not required to run OpenFOAM commands. System operations have been enabled in /opt/openfoam230/etc/controlDict. Note that virtualenv is no longer installed in this image.

As ParaView has been built with off-screen rendering using OSMesa, the typical workflow with paraFoam is not available and it is advised to convert data into VTK format using foamToVTK for post-processing via pvpython or pvbatch.

