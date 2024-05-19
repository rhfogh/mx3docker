
FROM ubuntu:22.04

# Set terminal and time zone, to catch installer interactoin attempts
#ENV TERM linux
#ENV TZ Europe/London
#RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y python2.7-minimal python-pip
RUN apt-get install -y openjdk-11-jre-headless

RUN pip2 install wheel
RUN pip2 install python-qt suds scipy pyqtgraph gevent jsonpickle pyyaml PyDispatcher pylint lxml jsonschema

RUN pip2 install py4j f90nml mgen

# GPhL code locations. Name is should match external directory structure,
# so that the same directory names work inside and outside the docker.
# RUN mkdir -p /archive
# RUN mkdir -p /scratch_fs1
# RUN mkdir -p /public/xtal
RUN mkdir -p /alt/rhfogh
RUN mkdir -p /MXCuBE/mxcube
WORKDIR /MXCuBE/mxcube



# Used instead of Entrypoint to allow alternative commands to be run
CMD ["bin/mxcube", "--pyqt4"]
