# docker-rrdcached

This is a generic docker container for [rrdcached](https://oss.oetiker.ch/rrdtool/doc/rrdcached.en.html). The container runs rrdcached 1.5.5-4, at the moment still hard coded on port 42217.

## 1 How To Run

### 1.1 Prerequisites

1. Ensure Docker is installed.

### 1.2 Basic commands to run the container

	docker run \
		-d \
		-p 42217:42217 \
		-v /data/rrd:/opt/librenms/rrd \
		--name rrdcached \
		furhouse/docker-rrdcached

## 2 Project Details

### 2.1 Factors Addressed by This Container

* Running rrdcached in a isolated container for a distributed installation of LibreNMS.

### 2.2 Factors to Be Addressed by This Container

* Allow modification of rrdcached service based on environment variables.

### 2.3  Acknowledgements

* [docker-librenms by jarischaefer](https://github.com/jarischaefer/docker-librenms), basically forked his repository and modified the build to just run rrdcached.
