FROM fabito/sipsimple

RUN sudo apt-get update && sudo apt-get upgrade -y && sudo apt-get install -y python-pip git
RUN sudo pip install --upgrade pip

RUN sudo git clone https://github.com/gnikoloudakis/sip_proxy.git

RUN sudo pip install -r sip_proxy/requirements.txt

WORKDIR /sip_proxy

EXPOSE 9090:9090

ENTRYPOINT [ "python" ]

CMD [ "sip_proxy.py" ]
