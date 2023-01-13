############################
# STEP 1 build executable binary
############################
FROM golang:1.19-alpine AS builder

WORKDIR $GOPATH/src/app/
COPY go/ ./

# Build the binary.
RUN go build -o /go/bin/hello

############################
# STEP 2 build a small image
############################
FROM scratch

# Copy our static executable.
COPY --from=builder /go/bin/hello /go/bin/hello

# Run the hello binary.
ENTRYPOINT ["/go/bin/hello"]
