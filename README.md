# Databox SDK

Meta-repository and Docker based test suite for Databox SDKs.

[![Circle CI](https://circleci.com/gh/databox/sdk-tests/tree/master.svg?style=svg)](https://circleci.com/gh/databox/sdk-tests/tree/master)

## SDKs

| Language / SDK                                              |   CI Status                                                                                                       |
|-------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------|
| [JavaScript](https://github.com/databox/databox-js)         | [![Build Status](https://travis-ci.org/databox/databox-js.svg)](https://travis-ci.org/databox/databox-js)         |
| [Ruby](https://github.com/databox/databox-ruby)             | [![Build Status](https://travis-ci.org/databox/databox-ruby.svg)](https://travis-ci.org/databox/databox-ruby)     |
| [Go](https://github.com/databox/databox-go)                 | [![Build Status](https://travis-ci.org/databox/databox-go.svg)](https://travis-ci.org/databox/databox-go)         |
| [PHP](https://github.com/databox/databox-php)               | [![Build Status](https://travis-ci.org/databox/databox-php.svg)](https://travis-ci.org/databox/databox-php)       |
| [Python](https://github.com/databox/databox-python)         | [![Build Status](https://travis-ci.org/databox/databox-python.svg)](https://travis-ci.org/databox/databox-python) |
| [Java](https://github.com/databox/databox-java)             | [![Build Status](https://travis-ci.org/databox/databox-java.svg)](https://travis-ci.org/databox/databox-java)     |

## Running suite

This repository contains [Dockerfile](Dockerfile) that can used as basis for testing [Databox](http://databox.com) SDKs. [Rake](sdks/Rakefile) is used to `pull` data from repositories run its unit tests and examples.

Pull source code from all SDKs, install dependencies and run all tests.

    docker run -ti databox-sdk /bin/bash -lc \
      "rake"

Run specific test suite (JavaScript SDK in this example):

    docker run -ti databox-sdk /bin/bash -lc \
      "rake clean js"

## Development

Help yourself with [boot2docker](http://boot2docker.io/) if you are on OSX.

    boot2docker init
    boot2docker up

Build databox-sdk image with local [Dockerfile](Dockerfile).

    docker build -t databox-sdk .

Image mounts `/sdks` folder. When developing, you can also mount local folder to container:

    docker run -ti -v `pwd`/sdks:/sdks databox-sdk /bin/bash -lc \
      "rake clean all"

## Author

- [Oto Brglez](https://github.com/otobrglez)

