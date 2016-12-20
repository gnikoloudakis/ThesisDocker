#FROM sgoblin/python3.5
FROM lmurawsk/python2.7
MAINTAINER Yannis <yannis@example.com>


RUN apt-get update && apt-get install -y git python-dev openssh-server

RUN apt-get update && apt-get install -y git build-essential autoconf libtool pkg-config python-opengl python-imaging python-pyrex python-pyside.qtopengl idle-python2.7 qt4-dev-tools qt4-designer libqtgui4 libqtcore4 libqt4-xml libqt4-test libqt4-script libqt4-network libqt4-dbus python-qt4 python-qt4-gl libgle3 python-dev
##################################  ssh setup #############################
RUN mkdir /var/run/sshd
RUN echo 'root:password' | chpasswd
RUN sed -i 's/PermitRootLogin without-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# SSH login fix. Otherwise user is kicked off after login
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd
#############################################################################

RUN pip install --upgrade pip

RUN git clone https://github.com/gnikoloudakis/ThesisAPELE.git

RUN pip install -r ThesisAPELE/service_logic/requirements.txt

WORKDIR /ThesisAPELE/service_logic/

EXPOSE 8082:8082
EXPOSE 22:22

ENTRYPOINT [ "python" ]

CMD [ "serviceLogic.py" ]
