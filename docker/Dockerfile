FROM alpine:latest

RUN apk add --no-cache git racket ca-certificates curl sqlite

WORKDIR /app

RUN git clone --depth=1 https://gitdab.com/cadence/breezewiki.git . \
    && raco pkg install --batch --auto --no-docs --skip-installed req-lib \
    && raco req -d

EXPOSE 10416

CMD ["racket", "dist.rkt"]