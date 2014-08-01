openfoam_2.3.0 Docker image
===========================

A Docker image bundling [OpenFOAM 2.3.0](http://openfoam.org/version2.3.0/) and useful utilities.

Image includes:

- Ubuntu 13.10 64-bit
- OpenFOAM 2.3.0
- Paraview 4.1.0 (and paraFoam)
- Python 2.7 & 3.3
- pip (pip2 and pip3)
- NumPy, SciPy, Matplotlib, Pillow (latest versions at build time via pip2/pip3)
- ImageMagick, FFmpeg
- Wget, cURL
- Zip, UnZip
- Vim

The OpenFOAM environment is configured for the "ubuntu" user, and system operations have been enabled in /opt/openfoam230/etc/controlDict. Note the virtualenv is no longer installed in this image.