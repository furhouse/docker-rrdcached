# docker-rrdcached

This is a generic docker container for [rrdcached](https://oss.oetiker.ch/rrdtool/doc/rrdcached.en.html). The container runs rrdcached 1.5.5-4, and is configurable with environment variables.

## 1 How To Run

### 1.1 Prerequisites

1. Ensure Docker is installed.

### 1.2 Basic commands to run the container

        docker run \
          -d \
          -p 42217:42217 \
          -e WRITE_TIMEOUT=900 \
          -e DELAY=900 \
          -e CACHE_TIMEOUT=1800 \
          -e PORT=41127 \
          -e WRITE_THREADS=6 \
          -v /data/rrd:/opt/librenms/rrd \
          --name rrdcached \
          furhouse/docker-rrdcached

### 1.3 Environment Variables

* WRITE_TIMEOUT         default         900
* DELAY                 default         900
* CACHE_TIMEOUT         default         1800
* PORT                  default         42217
* WRITE_THREADS         default         4

## 2 Project Details

### 2.1 Factors Addressed by This Container

* Running rrdcached in a isolated container for a distributed installation of LibreNMS.

### 2.2 Factors to Be Addressed by This Container

* TBD

### 2.3  Acknowledgements

* [docker-librenms by jarischaefer](https://github.com/jarischaefer/docker-librenms), basically forked his repository and modified the build to just run rrdcached.
