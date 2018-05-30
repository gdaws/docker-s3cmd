FROM alpine:3.3

RUN apk update
RUN apk add tar python py-pip py-setuptools ca-certificates
RUN pip install python-dateutil

ADD https://github.com/s3tools/s3cmd/releases/download/v2.0.1/s3cmd-2.0.1.tar.gz /opt/

RUN tar zxf /opt/s3cmd-2.0.1.tar.gz -C /opt

ADD ./s3cfg /root/.s3cfg

ENTRYPOINT ["/opt/s3cmd-2.0.1/s3cmd"]
