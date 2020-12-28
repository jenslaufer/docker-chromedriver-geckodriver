FROM alpine:3.8


# update apk repo
RUN sed -i -e 's/v[[:digit:]]\.[[:digit:]]/edge/g' /etc/apk/repositories && \
  echo "http://dl-4.alpinelinux.org/alpine/v3.8/main" >> /etc/apk/repositories && \
  echo "http://dl-4.alpinelinux.org/alpine/v3.8/community" >> /etc/apk/repositories && \
  echo "http://dl-cdn.alpinelinux.org/alpine/edge/testing" >> /etc/apk/repositories && \
  apk update && apk upgrade && \
  apk add chromium chromium-chromedriver && \
  apk add firefox && \
  wget https://github.com/mozilla/geckodriver/releases/download/v0.24.0/geckodriver-v0.24.0-linux64.tar.gz && \
  tar -xzf geckodriver-v0.24.0-linux64.tar.gz -C /usr/local/bin && \
  rm geckodriver-v0.24.0-linux64.tar.gz && \
  chmod +x /usr/local/bin/geckodriver && \
  rm -rf /var/cache/apk/*
