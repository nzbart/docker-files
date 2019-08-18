FROM debian:testing

LABEL description="Debian package development environment"
MAINTAINER Bart Joy

# install packages
ARG DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get -y full-upgrade
RUN apt-get install -y --no-install-recommends apt-utils
RUN apt-get install -y debmake vim mc pbuilder
RUN apt-get autoremove -y; apt-get clean; rm /var/lib/apt/lists/*; rm -rf /var/log/*;

RUN useradd -ms /bin/bash builder
RUN adduser builder sudo
RUN echo "builder ALL=(ALL) NOPASSWD:ALL" | sudo tee -a /etc/sudoers
RUN mkdir -p /src; chown builder:builder /src; echo 'cd /src' >> /home/builder/.bashrc
USER builder
WORKDIR /home/builder

ENTRYPOINT []

CMD ["/bin/bash"]
