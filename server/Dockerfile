
FROM debian:10-slim

ENV tmp_dir /tmp

RUN apt-get update \
  && apt-get install -y curl \
  && curl -sL https://deb.nodesource.com/setup_12.x | bash - \
  && apt-get install -y nodejs

RUN npm install -g json-server

RUN echo '{"storypoints": [{"value": 0.5},{"value": 1},{"value": 2},{"value": 3},{"value": 5},{"value": 8},{"value": 13}],"storyboard": []}' > /tmp/test.json

ENTRYPOINT ["json-server", "--port", "8080", "--host", "0.0.0.0"]

CMD ["/tmp/test.json"]