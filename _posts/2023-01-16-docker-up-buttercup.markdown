---
layout: post
title:  "Docker Up Buttercup"
date:   2023-01-16 21:31:41 +1300
categories: blog update
---
I wanted to spin up a quick Docker Image, to run as a build & test platform for the necessary Python libraries for the [Getting Started with Python for Quant Finance] course.

Some people do not like installing multiple packages to just do a narrow 'thing'.

I have no issue installing packages to do multiple things, such as OpenCV, Data Management and developing GUI applications but after a while, your OS starts to look like a local Ubuntu repository.

Fortunately, Docker exists, so we can install software to make an image, that we can repurpose as required. This post assumes no knowledge of Docker other than it exists, and a basic knowledge of and use in the Linux command line on an Ubuntu operating system.

**Current Dockerfile:**

{% highlight ruby %}

# syntax=docker/dockerfile:1

# Source OS Build
FROM ubuntu

# Set Working Directory
WORKDIR /ubuntu-test-v01

# Source All_Files
Copy . .

# Install required software
#
# TZDATA
# Python3
# SciPy; NumPy; Pandas; PyFinance; TensorFlow;
# PyBrain; PyMC3; PyQuant; PyTorch; PyAlgoTrade;
# QuantLib; PyThalesians; Quantopian; PySwarms; PyQuantLib

# Update system
RUN apt update

# Install lsb-release
RUN apt install -y --no-install-recommends lsb-release

# Install tzdata
# Need a custom config for Pacific/Auckland TZ
RUN apt -y install tzdata

# Install python3
# Investigate if existing Python installed and 
# consider an authscript to remove it completely
RUN apt -y install python3

# Install pip3
# Reminder: Pip can run as `pip` or `pip3`
RUN apt -y install python3-pip
# Install listed software re above
#
# RUN pip install -r requirements.txt
# Assume this method would just need a cleartext List
#
# RUN pip install scipy \
# numpy \
# pandas \
# pyfinance \
# tensorflow \
# pybrain \
# pymc3 \
# pyquant \
# pytorch \
# pyalgotrade \
# quantlib \
# pythalesians \
# quantopian \
# pyswarms \
# pyquantlib

# Verify Pip3 version
RUN pip --version

# Visualize the Build
EXPOSE 5577

# Run application
CMD ["/bin/bash"]

# EOF
{% endhighlight %}

Initially, I had this install sequence enabled however it consistently timedout when attempting to install the packages using `pip`:

{% highlight ruby %}
RUN pip install scipy \
# numpy \
# pandas \
# pyfinance \
# tensorflow \
# pybrain \
# pymc3 \
# pyquant \
# pytorch \
# pyalgotrade \
# quantlib \
# pythalesians \
# quantopian \
# pyswarms \
# pyquantlib
{% endhighlight %}

Once I have worked out why the Build fails while installing the multile-packages, I can try again.

I also wrote a quick & simle guide on howto create and use a Dockerfile.

**Build process:**

{% highlight ruby %}
# REF https://docs.docker.com/build/building/base-images/ 
# /home/datakumquat/Projects/docker/ubuntu-test-v01

# change to Docker build directory
$ cd ~/Projects/docker

# create new docker image directory
$ mkdir -p ubuntu-test-v01/

# change into new docker image directory
$ cd ubuntu-test-v01

# create new Dockerfile
$ touch Dockerfile

# input content into Dockerfile
$ nano Dockerfile

# <-- insert code -->
#
# Refer to the above Code Block
#
# <-- insert code -->

# build new docker image
$ pwd
/home/datakumquat/Projects/docker/ubuntu-test-v01
$ docker build .

# run default tests against new image
$ TBA

# start container using new image
$ docker run --it new_docker_image_name
{% endhighlight %}

Verdict?

FAIL.

However this was just a quick post, and as I test & adjust further, this document will be updated.

**References:**

[Getting Started with Python for Quant Finance]
[Create a base image]

[Create a base image]: https://docs.docker.com/build/building/base-images/
[Getting Started with Python for Quant Finance]: https://gettingstartedwithpythonforquantfinance.com/

