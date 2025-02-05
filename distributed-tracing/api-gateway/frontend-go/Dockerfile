FROM golang:1.22 AS build
ADD *.go /go/src/frontend/
RUN cd /go/src/frontend && go mod init && go mod tidy && go install

FROM debian:bookworm-slim
COPY --from=build /go/bin/frontend /bin/frontend
ENTRYPOINT ["/bin/frontend"]
