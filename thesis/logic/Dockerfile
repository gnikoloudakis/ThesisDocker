#FROM sgoblin/python3.5
FROM python
MAINTAINER Yannis <yannis@example.com>

RUN apt-get update && apt-get install -y git python-dev openssh-server

RUN pip install --upgrade pip

RUN git clone https://github.com/gnikoloudakis/ThesisAPELE.git

RUN pip install -r ThesisAPELE/service_logic/requirements.txt

WORKDIR /ThesisAPELE/service_logic/

EXPOSE 8082:8082

ENTRYPOINT [ "python" ]

CMD [ "serviceLogic.py" ]