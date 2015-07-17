FROM learninglayers/base

MAINTAINER Sadik Bakiu <bakiu@dbis.rwth-aachen.de>

# based on https://github.com/learning-layers/Layers-Dockerfiles/blob/master/tomcat/Dockerfile for installing java 8
# Environment variables
ENV JAVA_HOME="/usr/lib/jvm/java-8-oracle"
ENV PATH=$JAVA_HOME/bin:$PATH

RUN apt-get install -y	wget  \
						unzip \
						dos2unix

# Install Java 8
RUN apt-get install -yq software-properties-common && \
	add-apt-repository -y ppa:openjdk-r/ppa && \
	apt-get update && \
	apt-get install -y openjdk-8-jre

# Create mount point
RUN mkdir /build
WORKDIR /build

# Download and unzip newest build from CI server
# dos2unix fixes the "textfile open" error
CMD wget http://layers.dbis.rwth-aachen.de/jenkins/job/LAS2peer-AnnotationService/lastSuccessfulBuild/artifact/*zip*/archive.zip && \
	unzip archive.zip && \
	cd archive && \
	dos2unix bin/start_network.sh && \
	chmod +x bin/start_network.sh && \
	bin/start_network.sh  && \
	while true; do echo hello world; sleep 1; done

EXPOSE 8083