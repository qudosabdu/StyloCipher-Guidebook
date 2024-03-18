# FROM: Specify base image (command must be on the top of the Dockerfile)
FROM ubuntu

# RUN: To execute commands and create layers in the image
RUN apt-get update && apt-get install -y \
    package1 \
    package2 \
    && rm -rf /var/lib/apt/lists/*

# MAINTAINER: Used to mention the author or developer
MAINTAINER YourName

# ADD: Similar to copy but provides a feature to download files from the internet
ADD http://example.com/file.tar.gz /path/in/container/

# EXPOSE: To expose ports such as port 8080 for Tomcat server, for Nginx 80, etc
EXPOSE 8080

# WORKDIR: To set the working directory for a container
WORKDIR /path/to/working/directory

# CMD: Execute commands but during container creation
CMD ["executable","param1","param2"]

# ENTRYPOINT: Similar to CMD but has higher priority over CMD
ENTRYPOINT ["executable", "param1"]

# ENV: Environment variables like ARG
ENV key=value

# docker build -t filetest . : 
To build image in the current directory with filetest name

# 1. vi Dockerfile
# 2. FROM ubuntu
# 3. RUN apt-get update
# 4. WORKDIR /tmp
# 5. RUN echo "Hello World" > /tmp/testfile
# 6. ENV myName abdulqudoos
# 7. COPY testfile1 /tmp  
    touch test
# 8. tar -cvf test.tar test
    test tar gz /tmp
# 9. gzip test.tar
# 10. docker build -t filetest .
# 11. docker run -it filetest /bin/bash

# docker build -t filetest . :
# docker run -it filetest /bin/bash


