FROM rasa/rasa:latest-full 

USER root

WORKDIR /app
COPY . /app
COPY ./data /app/data
RUN sudo pip3 install --upgrade pip --user
RUN sudo pip3 install nltk
RUN sudo rasa train

# Switch back to a non-root user
USER 1001

VOLUME /app
VOLUME /app/data
VOLUME /app/models
VOLUME /app/external_data


CMD [ "run","-m","/app/models","--enable-api","--cors","*","--debug"]