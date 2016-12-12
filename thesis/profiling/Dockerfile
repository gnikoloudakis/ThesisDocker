#FROM sgoblin/python3.5
FROM lmurawsk/python2.7

MAINTAINER Yannis <yannis@example.com>

RUN apt-get update && apt-get install -y git

RUN git clone https://github.com/gnikoloudakis/ThesisAPELE.git

RUN pip install --upgrade pip

RUN pip install -r ThesisAPELE/profiling_service/requirements.txt

WORKDIR /ThesisAPELE/profiling_service

EXPOSE 8080:8080

ENTRYPOINT [ "python" ]

CMD [ "profilingService.py" ]
