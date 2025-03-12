FROM mxcube2_dev_qt4_gphl6

# RUN apt-get update

# RUN apt-get install python-pip -y
# RUN pip install --upgrade pip

# To get rid of error, that the ps command cannot be found
# RUN apt-get install procps -y

COPY OpenJDK11U-jre_x64_linux_hotspot_11.0.21_9.tar.gz /root
RUN mkdir -p /opt && cd /opt && tar xvf /root/OpenJDK11U-jre_x64_linux_hotspot_11.0.21_9.tar.gz && ln -s jdk-11.0.21+9-jre /opt/jdk11


# Add user and group so files on main machine get to belong to user instead of root
# NB this must be adjusted to the test user. TODO move to separate docker
# RUN groupadd -g 3001 gphl
#RUN useradd -g gphl -m -s /bin/tcsh -u 1158 rhfogh
# No longer makes home directory - this must be mounted externally at startup
# RUN useradd -g gphl -s /bin/tcsh -u 1158 rhfogh

# Directories:
#
# /MXCuBE/mxcube - MXCuBE code location is made in mx3_deb9_qt4
#
# GPhL code locations. Name is should match external directory structure,
# so that the same directory names work inside and outside the docker.
# RUN mkdir -p /archive
# RUN mkdir -p /scratch_fs1
# RUN mkdir -p /public/xtal
# RUN mkdir -p /alt/rhfogh


# Used instead of Entrypoint to allow alternative commands to be run
CMD ["bin/mxcube", "--pyqt4"]
