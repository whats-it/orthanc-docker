FROM bluelens/orthanc:dev

MAINTAINER bluehackmaster <master@bluehack.net>
LABEL Description="Orthanc, free DICOM server, with plugins for Mediviewer" Vendor="BlueHack Inc."

RUN apt-get update
RUN apt-get -y install libc6 libc6-dev
ADD ./download-plugins.sh ./download-plugins.sh
ADD ./libDwvOrthancPlugin.so ./libDwvOrthancPlugin.so
RUN bash ./download-plugins.sh

RUN rm ./download-plugins.sh

VOLUME [ "/var/lib/orthanc/db" ]
EXPOSE 4242
EXPOSE 8042

ENTRYPOINT [ "Orthanc" ]
CMD [ "/etc/orthanc/" ]
