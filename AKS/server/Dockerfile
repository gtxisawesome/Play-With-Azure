# Dockerfile References: https://docs.docker.com/engine/reference/builder/

# Start from golang v1.12 base image
FROM golang:1.12

# Add Maintainer Info
LABEL maintainer="Frank Gao <gtx.seattle@gmail.com>"

# Set the Current Working Directory inside the container
WORKDIR /go/src/github.com/gtxistxgao/Play-With-Azure/AKS/server

# Copy everything from the current directory to the PWD(Present Working Directory) inside the container
COPY . .

# Download all the dependencies
# https://stackoverflow.com/questions/28031603/what-do-three-dots-mean-in-go-command-line-invocations
RUN go get -d -v ./...

# Install the package
RUN go install -v ./...

RUN go build wikiserver.go

# This container exposes port 8080 to the outside world
EXPOSE 8080

# Run the executable
CMD ["./wikiserver"]