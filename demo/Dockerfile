FROM python:2.7-alpine

RUN apk add --no-cache \
    dbus \
    ttf-freefont

COPY demoapp/server.py /opt/demoapp/server.py
COPY demoapp/html/demo.css /opt/demoapp/html/demo.css
COPY demoapp/html/error.html /opt/demoapp/html/error.html
COPY demoapp/html/index.html /opt/demoapp/html/index.html
COPY demoapp/html/welcome.html /opt/demoapp/html/welcome.html

EXPOSE 7272 7272

ENTRYPOINT [ "/opt/demoapp/server.py" ]