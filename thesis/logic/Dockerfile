#FROM sgoblin/python3.5
FROM lmurawsk/python2.7
MAINTAINER Yannis <yannis@example.com>


RUN apt-get update && apt-get install -y git python-dev openssh-server

RUN apt-get update && apt-get install -y git build-essential autoconf libtool pkg-config python-opengl python-imaging python-pyrex python-pyside.qtopengl idle-python2.7 qt4-dev-tools qt4-designer libqtgui4 libqtcore4 libqt4-xml libqt4-test libqt4-script libqt4-network libqt4-dbus python-qt4 python-qt4-gl libgle3 python-dev


RUN pip install --upgrade pip

RUN git clone https://github.com/gnikoloudakis/ThesisAPELE.git

RUN pip install -r ThesisAPELE/service_logic/requirements.txt

WORKDIR /ThesisAPELE/service_logic/

EXPOSE 8082:8082
EXPOSE 22:22

ENTRYPOINT [ "python" ]

CMD [ "serviceLogic.py" ]
