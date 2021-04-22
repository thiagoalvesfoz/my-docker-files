FROM golang:1.7.3 AS builder
WORKDIR /go/src/github.com/thiagoalvesfoz/fullcycle/
COPY app/main.go .
RUN GOOS=linux && \
    go build main.go

FROM scratch
COPY --from=builder /go/src/github.com/thiagoalvesfoz/fullcycle/main .
ENTRYPOINT ["./main"]