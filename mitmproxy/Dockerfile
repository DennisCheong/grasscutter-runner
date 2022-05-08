FROM python:3.9.12-alpine
RUN apk --update --no-cache add py3-pip ca-certificates gcc libffi-dev python3-dev musl-dev openssl-dev g++ libxml2-dev\
 libxslt-dev libjpeg-turbo-dev zlib-dev tshark
RUN pip3 install --upgrade pip
RUN pip3 install mitmproxy
WORKDIR /app
VOLUME [ "/app" ]
EXPOSE 8080
CMD ["mitmdump", "-s", "proxy.py", "--ssl-insecure", "--set", "block_global=false", "--listen-port", "8080"]
