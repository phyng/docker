
FROM phyng/ubuntu:14.04
MAINTAINER phyng

# postgres pillow lxml M2Crypto geolibs
RUN apt-get update && apt-get install -y \
    libpq-dev python-dev \
    libtiff5-dev libjpeg8-dev zlib1g-dev \
    libfreetype6-dev liblcms2-dev libwebp-dev tcl8.6-dev tk8.6-dev python-tk \
    libxml2-dev libxslt1-dev python-lxml \
    swig \
    binutils libproj-dev gdal-bin \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN apt-get build-dep python-lxml

# https://github.com/docker-library/pypy
ENV PYPY_VERSION 4.0.1
RUN set -x \
	&& curl -SL "https://bitbucket.org/pypy/pypy/downloads/pypy-${PYPY_VERSION}-linux64.tar.bz2" \
		| tar -xjC /usr/local --strip-components=1

ENV PYTHON_PIP_VERSION 7.1.2
RUN curl -SL 'https://bootstrap.pypa.io/get-pip.py' | pypy \
	&& pip install --upgrade pip==$PYTHON_PIP_VERSION
