# FROM python:alpine3.19


# RUN apk add --no-cache \
#         build-base \
#         pcre-dev \
#         libffi-dev \
#     && pip3 install uwsgi setuptools \
#     && adduser --home /opt/server --disabled-password roboshop \
#     && mkdir -p /opt/server \
#     && chown roboshop:roboshop -R /opt/server


# WORKDIR /opt/server
# USER roboshop


# COPY --chown=roboshop:roboshop payment.ini payment.py rabbitmq.py requirements.txt ./
# RUN pip3 install -r requirements.txt


# EXPOSE 8080
# CMD ["uwsgi", "--ini", "payment.ini"]

FROM 384570460482.dkr.ecr.ap-south-1.amazonaws.com/platform/python-runtime:3.12-alpine-3.23.2

WORKDIR /opt/server

COPY . .

CMD ["uwsgi", "--ini", "payment.ini"]
