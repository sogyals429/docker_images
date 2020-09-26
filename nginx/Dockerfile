FROM nginx

LABEL "MAINTAINER"="SogyalSherpa"

COPY nginx.conf /etc/nginx/nginx.conf

# RUN groupadd -g 2000 microservice && useradd -g 2000 -s /bin/false -u 2000 microservice
# RUN mkdir -p /microservice/config && chown -R microservice:microservice /microservice/config
RUN apt-get update && apt-get upgrade -y && apt-get -y install python3 && apt-get -y install python3-pip && pip3 install --upgrade pip
RUN pip3 install awscli
RUN aws configure set s3.signature_version s3v4

ADD entrypoint.sh /

EXPOSE 80

# USER microservice
# WORKDIR "/microservice"

ENTRYPOINT [ "/bin/bash","/entrypoint.sh" ]