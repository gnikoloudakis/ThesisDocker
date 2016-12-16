#FROM sgoblin/python3.5
FROM lmurawsk/python2.7
MAINTAINER Yannis <yannis@example.com>

RUN apt-get update && apt-get install -y git python-dev

RUN pip install --upgrade pip

RUN git clone https://github.com/gnikoloudakis/ThesisAPELE.git

RUN pip install -r ThesisAPELE/positioning_service/requirements.txt

WORKDIR /ThesisAPELE/positioning_service/

EXPOSE 8081:8081

ENTRYPOINT [ "python" ]

CMD [ "positioning_service.py" ]
