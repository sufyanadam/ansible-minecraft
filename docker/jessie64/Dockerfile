# vim: set ft=dockerfile:

# Requires Ansible 1.8+ from jessie-backports.
FROM debian:jessie-backports

# Colour output.
ENV TERM=xterm

# Defaults to graphical.target.
RUN systemctl set-default multi-user.target

RUN apt-get update -y \
    && apt-get --no-install-recommends install -y \
      default-jdk \
      gcc \
      git \
      libffi-dev \
      libssl-dev \
      net-tools \
      python-dev \
      python-pip \
      ruby \
      sudo \
      tar \
    && apt-get autoremove \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

RUN pip install -U setuptools

# A newish version of ansible is required, so install from pip instead of from
# the old Debian package.
RUN pip install ansible

RUN gem install serverspec
