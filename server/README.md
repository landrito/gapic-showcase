# GAPIC Showcase Server
[![Release Level][releaselevelimg]][releaselevel]
[![CircleCI][circleimg]][circle]
[![Code Coverage][codecovimg]][codecov]
[![GoDoc][godocimg]][godoc]

> A server to test generated clients.

This is a server used to test the features of GAPICs (Generated API Client)
generated by the gapic-generators in [googleapis](https://github.com/googleapis).
Below is listed the patterns and features that can be tested using this API
alongside test cases that should be tested to verify that a GAPIC implements
the pattern or feature in question.

## Usage
```sh
# Install the server
go get github.com/googlapis/gapic-showcase

# Spin up the server. Opens port 8080 to accept requests.
go run $GOPATH/src/github.com/googleapis/gapic-showcase/cmd/server/main.go
```

## Pattern and Feature Test Cases

### Unary

- Single string request
- Server error

### Server Side Streaming

- Simple string request
- Error on first request
- Error after successful stream responses

### Client Side Streaming

- Passing two strings on the stream
- Error on first request
- Error after strings have been passed on the stream

### Bidirectional Streaming

- Simple request
- Error on first request
- Error after strings have been passed on the stream.

### Automatic Timeout Handling

- Responding immediately with success
- Responding after the client should timeout with success
- Responding immediately with an error
- Responding after the client should timeout with an error

### Automatic Retry Handling

- Successful at first call
- Multiple retry-able errors terminating in success
- Multiple retry-able errors terminating with an non retry-able error

### Long Running Operations

- Operation success on first call
- Operation success after small amount of time.
- Operation success after time to live limit is exceeded for a channel
- Operation error on first call
- Operation error after small amount of time.
- Operation metadata handling


### Automatic Paging

- Successful pagination up to response limit.
- API Call returning fewer items than page size
- API Call returning more items than page size.

### Parameter Flattening

- Single Field Flattening
- Repeated Field Flattening
- Nested Object Flattening

### Resource Naming

- Field which has a single pattern
- Field which can have multiple patterns

[circle]: https://circleci.com/gh/googleapis/gapic-showcase
[circleimg]: https://circleci.com/gh/googleapis/gapic-showcase.svg?style=shield
[codecovimg]: https://codecov.io/github/googleapis/gapic-showcase/coverage.svg?branch=master
[codecov]: https://codecov.io/github/googleapis/gapic-showcase?branch=master
[godoc]: https://godoc.org/github.com/googleapis/gapic-showcase/server
[godocimg]: https://godoc.org/github.com/googleapis/gapic-showcase/server?status.svg
[releaselevel]: https://cloud.google.com/terms/launch-stages
[releaselevelimg]: https://img.shields.io/badge/release%20level-pre%20alpha-red.svg?style&#x3D;flat
