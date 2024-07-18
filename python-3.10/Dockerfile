FROM python:3.10.11-slim

# Install git, wget, unzip, and libaio1
RUN apt-get update && \
    apt-get install -y git wget unzip libaio1

# Install Oracle Instant Client
RUN mkdir -p /opt/oracle && \
    cd /opt/oracle && \
    wget https://download.oracle.com/otn_software/linux/instantclient/2114000/instantclient-basic-linux.x64-21.14.0.0.0dbru.zip && \
    unzip instantclient-basic-linux.x64-21.14.0.0.0dbru.zip && \
    rm -f instantclient-basic-linux.x64-21.14.0.0.0dbru.zip && \
    cd instantclient* && \
    rm -f *jdbc* *occi* *mysql* *jar uidrvci genezi adrci && \
    echo /opt/oracle/instantclient* > /etc/ld.so.conf.d/oracle-instantclient.conf && \
    ldconfig

# Set environment variables for Oracle Instant Client
ENV LD_LIBRARY_PATH="/opt/oracle/instantclient_21_14:${LD_LIBRARY_PATH}"
ENV PATH="/opt/oracle/instantclient_21_14:${PATH}"