FROM alpine:3.8


# update apk repo
RUN sed -i -e 's/v[[:digit:]]\.[[:digit:]]/edge/g' /etc/apk/repositories
RUN echo "http://dl-4.alpinelinux.org/alpine/v3.8/main" >> /etc/apk/repositories && \
    echo "http://dl-4.alpinelinux.org/alpine/v3.8/community" >> /etc/apk/repositories && \
    echo "http://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories

RUN apk update && apk upgrade


# install chromedriver
RUN apk add chromium chromium-chromedriver

# install firefox and geckodriver
RUN apk add firefox
RUN wget https://github.com/mozilla/geckodriver/releases/download/v0.24.0/geckodriver-v0.24.0-linux64.tar.gz
RUN tar -xzf geckodriver-v0.24.0-linux64.tar.gz -C /usr/local/bin &&\
    rm geckodriver-v0.24.0-linux64.tar.gz

RUN chmod +x /usr/local/bin/geckodriver

RUN rm -rf /var/cache/apk/*
