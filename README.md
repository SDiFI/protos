# SDiFI Protocol Buffer Specifications

This repository contains Protobuf specifications for messages and services used
by the SDiFI project. [buf](https://buf.build) is used to lint, format and
manage dependecies (currently only a small subset of googleapis).

To lint all protos in the repo:

``` shell
buf lint
```

To format all protos in the repo:

``` shell
buf format -w
```

To gather all protos, ours and imported dependencies into the directory `gen`:

``` shell
buf export -o gen
```

You can use `buf` to generate code for your language with plugins. For Ruby
create a `buf.gen.yaml` file:

``` yaml
# buf.gen.yaml
version: v1
managed:
  enabled: true
plugins:
  - plugin: buf.build/protocolbuffers/ruby:v24.3
    out: gen
```

and run:

``` shell
buf generate --include-imports
```

to generate Ruby code in the directory `gen`.

