FROM ubuntu:20.04

# Set terminal and time zone, to catch installer interactoin attempts
ENV TERM linux
ENV TZ Europe/London
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone

# Install system packages - from Marcus O mxcub3
RUN apt-get update && apt-get -y upgrade && \
    apt-get install -y apt-utils curl git sudo wget python
RUN apt-get install -y build-essential

# Get and update pip
RUN apt-get install python3-pip -y
RUN pip install --upgrade pip

# From requirement list
RUN pip install gevent==21.12.0
RUN pip install greenlet==1.1.2
RUN pip install jsonpickle==2.2.0
RUN pip install jsonschema==4.6.1
RUN pip install lxml==4.9.1
RUN pip install matplotlib==3.5.2
RUN pip install numpy==1.23.0
RUN pip install Pillow==9.2.0
RUN pip install pydantic==1.9.1
RUN pip install PyDispatcher==2.0.5
RUN pip install pylint==2.14.4
RUN pip install ruamel.yaml==0.17.21
RUN pip install scipy==1.8.1
RUN pip install suds-py3==1.4.5.0
RUN pip install psutil==5.9.1
RUN pip install gipc==1.4.0

RUN apt-get install -y python3-pyqtgraph

# GPhL: f90nml, and py4j are required for GPhL Workflow and emulation
RUN pip install py4j==0.10.9.5
RUN pip install f90nml==1.4.3
