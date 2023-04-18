FROM golang:alpine AS builder

WORKDIR /app

COPY main.go go.mod ./

RUN GOOS=linux GOARCH=amd64 go build -ldflags="-w -s" -o /go/bin/hello

FROM scratch

COPY --from=builder /go/bin/hello /app/hello

ENTRYPOINT [ "/app/hello" ]