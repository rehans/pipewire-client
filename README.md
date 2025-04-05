# PipeWire Client

## Introduction

Pipewire client just to play around with the PipeWire API

## Get Started

To clone and create the project, open a command prompt and proceed as follows:

### Linux

```
git clone https://www.github.com/rehans/pipewire-client.git
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ../pipewire-client
cmake --build .
```

## Inspect PipeWire

In terminal:

* `ps -e | grep pipewire`
* `pw-cli list-objects Device`
* `systemctl --user list-unit-files | grep -E 'pulse|wire' | awk '{ print $1,"-", $2 }'`

## Get Help

* https://docs.pipewire.org/page_api.html