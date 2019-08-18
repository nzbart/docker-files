FROM debian:testing

LABEL description="Debian package development environment"
MAINTAINER Bart Joy

# install packages
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update; \
    apt-get install -y --no-install-recommends apt-utils; \
    apt-get install -y debmake fakeroot vim; \
    apt-get autoremove -y; \
    apt-get clean; \
    rm /var/lib/apt/lists/*; \
    rm -rf /var/log/*;

# prepare work dir
RUN mkdir -p /src; chown builder:builder /src; echo 'cd /src' >> /home/builder/.bashrc

# remove previous entrypoint
ENTRYPOINT []

CMD ["/bin/bash"]
