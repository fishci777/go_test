FROM golang:alpine as builder
WORKDIR /go/src/github.com/app
COPY . .
RUN go build -o app ./project1

###
FROM alpine:latest
COPY --from=builder /go/src/app/app /usr/local/bin/
EXPOSE 8081
ENTRYPOINT [ "/usr/local/bin/app" ]
