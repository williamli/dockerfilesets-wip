#
# Node.js Dockerfile
#
#

# Pull base image.
FROM ubuntu:13.10
MAINTAINER William Li, williamli@quriousone.io

# Install Node.js
#RUN apt-get install -y software-properties-common
#RUN add-apt-repository -y ppa:chris-lea/node.js
RUN apt-get update
RUN apt-get install -y nodejs
RUN ln -fs /usr/bin/nodejs /usr/bin/node
RUN curl https://npmjs.org/install.sh | sh

RUN apt-get install -y vim

# Bundle app source
ADD . /app

# Install app dependencies
#RUN cd /src; npm install


# Append to $PATH variable.
RUN echo '\n# Node.js\nexport PATH="/app/node_modules/.bin:$PATH"' >> /root/.bash_profile

EXPOSE  8080

# Define entrypoint, cmd can be used in docker run to point to different nodejs start file
ENTRYPOINT ["node"]
