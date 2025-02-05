FROM golang:1.22 AS build
ADD *.go /go/src/quotes/
RUN cd /go/src/quotes && go mod init && go mod tidy && go install

FROM debian:bookworm-slim
COPY --from=build /go/bin/quotes /bin/quotes
ENTRYPOINT ["/bin/quotes"]
