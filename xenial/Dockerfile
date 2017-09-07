FROM ubuntu:16.04

RUN apt-get -y update && apt-get install -y python-dev libffi-dev libssl-dev  python-minimal python-pip ca-certificates  && pip install -U pip &&  pip install virtualenv pyopenssl ndg-httpsclient pyasn1

# Clean up APT when done.
RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

