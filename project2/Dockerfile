FROM golang:alpine as builder
WORKDIR /go/src/github.com/matpool
COPY . .
RUN go build -o app ./project2

###
FROM alpine:latest
COPY --from=builder /go/src/github.com/matpool/app /usr/local/bin/
EXPOSE 8082
ENTRYPOINT [ "/usr/local/bin/app" ]
