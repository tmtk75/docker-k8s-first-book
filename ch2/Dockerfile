FROM golang:1.9 AS golang

WORKDIR /
COPY main.go /
RUN CGO_ENABLED=0 GOOS=linux GOARCH=amd64 \
      go build -a -installsuffix cgo \
      -o echo main.go


FROM busybox
#FROM alpine
COPY --from=golang /echo /
RUN chmod +x /echo

CMD ["/echo"]
