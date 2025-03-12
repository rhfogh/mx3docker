FROM ubuntu:22.04

RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y git vim software-properties-common
RUN apt-get install -y python2.7-minimal python-pip libpython2.7-dev
RUN apt-get install -y openjdk-11-jre-headless

RUN add-apt-repository -y ppa:ubuntuhandbook1/ppa && apt-get update
RUN apt-get install -y qt4-default

RUN pip2 --no-python-version-warning install wheel
RUN pip2 --no-python-version-warning install python-qt suds scipy pyqtgraph gevent jsonpickle pyyaml PyDispatcher pylint lxml jsonschema

RUN pip2 --no-python-version-warning install py4j f90nml mgen

ADD PyQt4_commercial_x11-4.12.3.tar.gz /root
ADD sip-4.19.25.tar.gz /root
COPY pyqt-commercial.sip /root/PyQt4_commercial_x11-4.12.3/sip
RUN cd /root/sip-4.19.25 && python2 configure.py --sip-module PyQt4.sip --no-dist-info && make && make install
# Newer configure-ng.py doesn't work here.
RUN cd /root/PyQt4_commercial_x11-4.12.3 && python2 configure.py --confirm-license && make && make install
