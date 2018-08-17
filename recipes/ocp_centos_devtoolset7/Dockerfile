# Copyright (c) 2012-2017 Red Hat, Inc
# All rights reserved. This program and the accompanying materials
# are made available under the terms of the Eclipse Public License v1.0
# which accompanies this distribution, and is available at
# http://www.eclipse.org/legal/epl-v10.html

FROM registry.centos.org/che-stacks/centos-stack-base

MAINTAINER Pawel Josefsson

USER root

RUN yum groupinstall -y "Development Tools" && \
    yum install -y centos-release-scl-rh && \
    INSTALL_PKGS="docker-client devtoolset-7-gcc devtoolset-7-gcc-c++ devtoolset-7-gcc-gfortran devtoolset-7-gdb" && \
    yum install -y --setopt=tsflags=nodocs $INSTALL_PKGS && \
    rpm -V $INSTALL_PKGS && \
    yum clean all -y && \
    cat /opt/rh/devtoolset-7/enable >> /home/user/.bashrc

USER user

