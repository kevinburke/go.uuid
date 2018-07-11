# UUID package for Go language

This is a fork of satori/go.uuid that won't change the existing API. I am
committed to maintaining this fork and responding to bug reports as appropriate.

Note the upstream satori/go.uuid [has a critical error][error] that may lead to
non-random UUID's. This fork is not vulnerable to that issue.

[error]: https://github.com/satori/go.uuid/issues/73#issuecomment-378573107

[![Build Status](https://travis-ci.org/kevinburke/go.uuid.png?branch=master)](https://travis-ci.org/kevinburke/go.uuid)
[![Coverage Status](https://coveralls.io/repos/github/kevinburke/go.uuid/badge.svg?branch=master)](https://coveralls.io/github/kevinburke/go.uuid)
[![GoDoc](http://godoc.org/github.com/kevinburke/go.uuid?status.png)](http://godoc.org/github.com/kevinburke/go.uuid)

This package provides a pure Go implementation of Universally Unique Identifiers
(UUIDs). Supports both creation and parsing of UUIDs.

With 100% test coverage and benchmarks out of box.

Supported versions:
* Version 1, based on timestamp and MAC address (RFC 4122)
* Version 2, based on timestamp, MAC address and POSIX UID/GID (DCE 1.1)
* Version 3, based on MD5 hashing (RFC 4122)
* Version 4, based on random numbers (RFC 4122)
* Version 5, based on SHA-1 hashing (RFC 4122)

The most common UUID used today is v4, which provides a random sequence of 16
bytes.

## Installation

Use the `go` command:

	$ go get github.com/kevinburke/go.uuid

## Requirements

UUID package requires Go >= 1.5.

## Example

```go
package main

import (
	"fmt"

	"github.com/kevinburke/go.uuid"
)

func main() {
	// Creating UUID Version 4
	u1 := uuid.NewV4()
	fmt.Printf("UUIDv4: %s\n", u1)

	// Parsing UUID from string input
	u2, err := uuid.FromString("6ba7b810-9dad-11d1-80b4-00c04fd430c8")
	if err != nil {
		fmt.Printf("Something gone wrong: %s", err)
	}
	fmt.Printf("Successfully parsed: %s", u2)
}
```

## Documentation

[Documentation](http://godoc.org/github.com/kevinburke/go.uuid) is hosted at GoDoc.

## Links

* [RFC 4122](http://tools.ietf.org/html/rfc4122)
* [DCE 1.1: Authentication and Security Services](http://pubs.opengroup.org/onlinepubs/9696989899/chap5.htm#tagcjh_08_02_01_01)

## Copyright

Copyright (C) 2013-2018 by Maxim Bublis <b@codemonkey.ru>. Copyright 2018 Kevin
Burke.

UUID package is released under the MIT License.
See [LICENSE](https://github.com/kevinburke/go.uuid/blob/master/LICENSE) for details.
