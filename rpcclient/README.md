rpcclient
=========

[![Build Status](http://img.shields.io/travis/hunjixin/hxd2.svg)](https://travis-ci.org/hunjixin/hxd2)
[![ISC License](http://img.shields.io/badge/license-ISC-blue.svg)](http://copyfree.org)
[![GoDoc](https://img.shields.io/badge/godoc-reference-blue.svg)](http://godoc.org/github.com/hunjixin/hxd2/rpcclient)

rpcclient implements a Websocket-enabled Decred JSON-RPC client package written
in [Go](http://golang.org/).  It provides a robust and easy to use client for
interfacing with a Decred RPC server that uses a hxd2 compatible Decred
JSON-RPC API.

## Status

This package is currently under active development.  It is already stable and
the infrastructure is complete.  However, there are still several RPCs left to
implement and the API is not stable yet.

## Documentation

* [API Reference](http://godoc.org/github.com/hunjixin/hxd2/rpcclient)
* [hxd2 Websockets Example](https://github.com/hunjixin/hxd2/tree/master/rpcclient/examples/hxd2websockets)
  Connects to a hxd2 RPC server using TLS-secured websockets, registers for
  block connected and block disconnected notifications, and gets the current
  block count
* [dcrwallet Websockets Example](https://github.com/hunjixin/hxd2/tree/master/rpcclient/examples/dcrwalletwebsockets)  
  Connects to a dcrwallet RPC server using TLS-secured websockets, registers for
  notifications about changes to account balances, and gets a list of unspent
  transaction outputs (utxos) the wallet can sign

## Major Features

* Supports Websockets (hxd2/dcrwallet) and HTTP POST mode (bitcoin core-like)
* Provides callback and registration functions for hxd2/dcrwallet notifications
* Supports hxd2 extensions
* Translates to and from higher-level and easier to use Go types
* Offers a synchronous (blocking) and asynchronous API
* When running in Websockets mode (the default):
  * Automatic reconnect handling (can be disabled)
  * Outstanding commands are automatically reissued
  * Registered notifications are automatically reregistered
  * Back-off support on reconnect attempts

## Installation

```bash
$ go get -u github.com/hunjixin/hxd2/rpcclient
```

## License

Package rpcclient is licensed under the [copyfree](http://copyfree.org) ISC
License.
