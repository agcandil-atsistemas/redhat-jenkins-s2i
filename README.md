# Jenkins RHEL7

This repository contains s2i code to customize openshift3/jenkins-2-rhel7 image

## Requeriment
### Install s2i https://github.com/openshift/source-to-image
For Linux
Go to the releases page and download the correct distribution for your machine. Choose either the linux-386 or the linux-amd64 links for 32 and 64-bit, respectively.

Unpack the downloaded tar with

$ tar -xvf release.tar.gz.

You should now see an executable called s2i. Either add the location of s2i to your PATH environment variable, or move it to a pre-existing directory in your PATH. For example,

* cp /path/to/s2i /usr/local/bin

will work with most setups.
