FROM fabito/sipsimple

RUN sudo pip install --upgrade pip

RUN sudo git clone https://github.com/gnikoloudakis/sip_proxy.git

RUN sudo pip install -r sip_proxy/requirements.txt

WORKDIR /sip_proxy

EXPOSE 5000:5000

ENTRYPOINT [ "python2" ]

CMD [ "sip_proxy.py" ]
