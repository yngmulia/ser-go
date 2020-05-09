# Start from the latest golang base image
FROM golang:latest

# Add Maintainer Info
LABEL maintainer="Rajeev Singh <rajeevhub@gmail.com>"

RUN go version

# Set the Current Working Directory inside the container
WORKDIR /app

RUN git clone https://github.com/yngmulia/citra-digital-test.git

WORKDIR /app/citra-digital-test

# Download all dependencies. Dependencies will be cached if the go.mod and go.sum files are not changed
RUN go mod download
RUN go mod vendor

RUN ls

# Build the Go app
# RUN go build -o main .
RUN go build main.go

# Expose port 8080 to the outside world
EXPOSE 8080

# Command to run the executable
CMD ["./main"]