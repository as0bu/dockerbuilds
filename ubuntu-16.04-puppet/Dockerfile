FROM ubuntu:16.04
MAINTAINER Taylor Owen (as0bu)

ARG AGENT_VERSION=""

RUN apt-get update && \
    apt-get install -y wget && \
    wget https://apt.puppetlabs.com/puppetlabs-release-pc1-xenial.deb && \
    dpkg -i puppetlabs-release-pc1-xenial.deb && \
    rm puppetlabs-release-pc1-xenial.deb && \
    apt-get update && \
    apt-get install -y $(if [ -z "$AGENT_VERSION" ]; then echo "puppet-agent"; else echo "puppet-agent=$AGENT_VERSION-1xenial"; fi) && \
    apt-get remove --purge -y wget && \
    apt-get autoremove -y && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

ENV PATH=$PATH:/opt/puppetlabs/bin
