FROM python:3.8

RUN curl https://install.spacetimedb.com/install-script.sh > spacetime.sh
RUN chmod +x spacetime.sh
RUN cat spacetime.sh
RUN ./spacetime.sh

# Get and setup ttyd, which will provide a browser based interface to a terminal from within the container
RUN wget https://github.com/tsl0922/ttyd/releases/download/1.7.3/ttyd.x86_64 
RUN mkdir /ttyd
RUN mv ttyd.x86_64 /ttyd/ttyd
RUN chmod 777 /ttyd/ttyd
ENTRYPOINT spacetime server add http://spacetime:3000 lde && spacetime server set-default lde && /ttyd/ttyd bash
