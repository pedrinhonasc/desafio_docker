FROM golang:alpine as builder

WORKDIR /go/src

COPY ./main.go .

RUN GOOS=linux go build -o /go/bin/hello main.go

FROM scratch

COPY --from=builder /go/bin/hello /go/bin/hello

ENTRYPOINT [ "/go/bin/hello" ]