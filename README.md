# httpstat [![Build Status](https://github.com/davecheney/httpstat/actions/workflows/push.yml/badge.svg)](https://github.com/davecheney/httpstat/actions/workflows/push.yml) [![Go Report Card](https://goreportcard.com/badge/github.com/davecheney/httpstat)](https://goreportcard.com/report/github.com/davecheney/httpstat)

![Shameless](./screenshot.png)

Imitation is the sincerest form of flattery.

But seriously, https://github.com/reorx/httpstat is the new hotness, and this is a shameless rip off.

## Installation
`httpstat` requires Go 1.20 or later.
```
$ go install github.com/davecheney/httpstat@latest
```

## Usage
```
$ httpstat https://example.com/
```
## Features

- Windows/BSD/Linux supported.
- HTTP and HTTPS are supported, for self signed certificates use `-k`.
- Skip timing the body of a response with `-I`.
- Follow 30x redirects with `-L`.
- Change HTTP method with `-X METHOD`.
- Provide a `PUT` or `POST` request body with `-d string`. To supply the `PUT` or `POST` body as a file, use `-d @filename`.
- Add extra request headers with `-H 'Name: value'`.
- The response body is usually discarded, you can use `-o filename` to save it to a file, or `-O` to save it to the file name suggested by the server.
- HTTP/HTTPS proxies supported via the usual `HTTP_PROXY`/`HTTPS_PROXY` env vars (as well as lower case variants).
- Supply your own client side certificate with `-E cert.pem`.

## New Feature: JSON Output

I've made some modifications to this project to allow output in JSON format. You can use the `-F` flag to get results in JSON format. Here's an example command and output:

Command:

`httpstat -F https://example.com`

Output:

```json
{
 "dns_lookup": 0,
 "tcp_connection": 0,
 "tls_handshake": 764,
 "server_processing": 260,
 "content_transfer": 0,
 "namelookup": "0",
 "connect": "0",
 "pretransfer": "767",
 "starttransfer": "1028",
 "total": "1029",
 "connection_protocol": "TLSv1.3",
 "connection_time": "764"
}
```

This result can now be directly used for data storage, analysis or other purposes.


## Contributing

Bug reports are most welcome, but with the exception of #5, this project is closed.

Pull requests must include a `fixes #NNN` or `updates #NNN` comment. 

Please discuss your design on the accompanying issue before submitting a pull request. If there is no suitable issue, please open one to discuss the feature before slinging code. Thank you.
