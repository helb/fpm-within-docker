FROM fedora:28
MAINTAINER Jiri Helebrant <helb@helb.cz>
RUN dnf clean metadata \
 && dnf -y update \
 && dnf -y install \
    @"Development Tools" \
    gnupg \
    libffi \
    libffi-devel \
    rpm-build \
    rpm-sign \
    rsync \
    ruby \
    ruby-devel \
    rubygems \
 && dnf clean all
RUN gem install --no-ri --no-rdoc fpm -v 1.9.3
