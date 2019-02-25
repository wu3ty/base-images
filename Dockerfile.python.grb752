FROM ubuntu:latest

RUN apt update && apt install \
    wget python3 python3-distutils python3-pip  --assume-yes

# setup Gurobi 7.5.2
RUN wget https://packages.gurobi.com/7.5/gurobi7.5.2_linux64.tar.gz && tar xvfz gurobi7.5.2_linux64.tar.gz && rm gurobi7.5.2_linux64.tar.gz
RUN mv gurobi752 /opt/ && cd /opt/gurobi752/linux64/ && python3 setup.py install
ENV GUROBI_HOME="/opt/gurobi752/linux64"
ENV PATH="${PATH}:${GUROBI_HOME}/bin"
ENV LD_LIBRARY_PATH="${LD_LIBRARY_PATH}:${GUROBI_HOME}/lib"

# license file should be created by app
ENV GRB_LICENSE_FILE="/gurobi.lic"

WORKDIR /
