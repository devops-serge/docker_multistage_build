# Use the official Golang image as the base image
FROM golang:1.20

# Set the Current Working Directory inside the container
WORKDIR /app

# Copy the go.mod files
COPY go.mod ./

# Download all the dependencies
RUN go mod download

# Copy the source code into the container
COPY main.go .

# Build the Go app
RUN GOOS=linux GOARCH=amd64 go build -ldflags="-w -s"  -o hello

# Command to run the executable
ENTRYPOINT ["/app/hello"]
