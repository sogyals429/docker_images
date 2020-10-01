FROM nginx

LABEL "MAINTAINER"="SogyalSherpa"

COPY nginx.conf /etc/nginx/nginx.conf

RUN apt-get update && apt-get upgrade -y && apt-get -y install python3 && apt-get -y install python3-pip && pip3 install --upgrade pip
RUN pip3 install awscli
RUN aws configure set s3.signature_version s3v4

ADD entrypoint.sh /

EXPOSE 80

ENTRYPOINT [ "/bin/bash","/entrypoint.sh" ]