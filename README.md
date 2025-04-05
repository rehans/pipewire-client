# PipeWire Client

## Introduction

Pipewire client just to play around with the PipeWire API

## Prepare Linux

Make sure that PipeWire is working correctly on Linux. 

### Manjaro

Deinstall Pulse Audio and install PipeWire in terminal:

* `sudo pacman -Rdd pulseaudio`
* `sudo pacman -S pipewire pipewire-pulse pipewire-jack pipewire-alsa pipewire-media-session`

> Restart afterwards and check if the PipeWire server is running by using `inxi -Azy`

## Get Started

### Linux

To clone and create the project, open a command prompt and proceed as follows:

```
git clone https://www.github.com/rehans/pipewire-client.git
mkdir build
cd build
cmake -DCMAKE_BUILD_TYPE=Debug ../pipewire-client
cmake --build .
```

## Inspect PipeWire

In terminal:

* Check PipeWire Server: `inxi -Azy` 
* List PipeWire processes: `ps -e | grep pipewire`
* List connected devices: `pw-cli list-objects Device`
* `systemctl --user list-unit-files | grep -E 'pulse|wire' | awk '{ print $1,"-", $2 }'`

## Get Help

* https://docs.pipewire.org/page_api.html
* https://wiki.ubuntuusers.de/Pipewire (german)