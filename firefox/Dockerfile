FROM python:2.7-alpine

RUN apk add --no-cache \
    dbus \
    ttf-freefont \
    firefox-esr \
    xvfb

RUN pip install --no-cache-dir \
  robotframework==3.0.2 \
  robotframework-selenium2library==1.8.0 \
  selenium==2.53.6

COPY entry_point.sh /opt/bin/entry_point.sh
RUN chmod +x /opt/bin/entry_point.sh

COPY demoapp/server.py /opt/demoapp/server.py
COPY demoapp/html/demo.css /opt/demoapp/html/demo.css
COPY demoapp/html/error.html /opt/demoapp/html/error.html
COPY demoapp/html/index.html /opt/demoapp/html/index.html
COPY demoapp/html/welcome.html /opt/demoapp/html/welcome.html

ENV SCREEN_WIDTH 1280
ENV SCREEN_HEIGHT 720
ENV SCREEN_DEPTH 16

ENTRYPOINT [ "/opt/bin/entry_point.sh" ]