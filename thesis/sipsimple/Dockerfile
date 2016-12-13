FROM ubuntu:16.04

MAINTAINER Fábio Uechi <fabio.uechi@gmail.com>

RUN apt-get purge -y python.*

RUN apt-get update && apt-get install -y python curl wget git

RUN set -x \
	&& curl -SL 'https://bootstrap.pypa.io/get-pip.py' | python2 \
    && pip install --no-cache-dir virtualenv

RUN wget http://download.ag-projects.com/agp-debian-gpg.key -P /tmp/ && \
    apt-key add /tmp/agp-debian-gpg.key && \
	echo "deb    http://ag-projects.com/ubuntu trusty main" | tee -a /etc/apt/sources.list.d/ag-projects.list    

RUN apt-get update && \
	apt-get install -y python-sipsimple sipclients

#CMD ["/bin/bash"] 

RUN pip install --upgrade pip

RUN git clone https://github.com/gnikoloudakis/sip_proxy.git

RUN pip install -r sip_proxy/requirements.txt

WORKDIR /sip_proxy

EXPOSE 5000:5000

ENTRYPOINT [ "python2" ]

CMD [ "sip_proxy.py" ]
