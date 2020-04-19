# envctl [![Travis-CI](https://travis-ci.org/m-mizutani/envctl.svg)](https://travis-ci.org/m-mizutani/envctl) [![Report card](https://goreportcard.com/badge/github.com/m-mizutani/envctl)](https://goreportcard.com/report/github.com/m-mizutani/envctl)

CLI Environment Variable Controller in Go

```sh
$ cat setting.env
DB_NAME = AWESOME_DATABASE
$ cat sample.py
import os
print("my database is {0}".format(os.environ["DB_NAME"]))
$ envctl -e setting.env python sample.py
my database is AWESOME_DATABASE
```

## Install

```
$ go get -u github.com/m-mizutani/envctl
```

## Usage

### Read variables from env file

Sample `yourfile.env`
```
# Comment out is available
KEY1 = ABC
KEY2 = BCD
```

```sh
$ envctl -e yourfile.env <command> [arg1, [arg2, [...]]]
```

### Read variables from JSON file

Sample `yourfile.json`. JSON file must be map format with pairs of key(string) and value(string).
```json
{
    "KEY1": "ABC",
    "KEY2": "BCD"
}
```

```sh
$ envctl -e yourfile.json <command> [arg1, [arg2, [...]]]
```

## License

- MIT License
- Author: mizutani@sfc.wide.ad.jp
