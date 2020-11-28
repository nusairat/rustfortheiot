# Rasp Pi MQ

## Install
Need to make sure capnpn is installed first.

https://capnproto.org/install.html
- all the installation instructions are there

## BUILD
Will first need to build the image that Cross is going to make use of 
`docker build -t capnp-ubuntu:gnu`

Next you can cross compile the code so it is deployable to our Raspberry Pi:
`cross build --target=armv7-unknown-linux-gnueabihf`

You will then find the file in :

`target/armv7-unknown-linux-gnueabihf/debug/rasp-pi-mq`

## Copy to the Pi
scp target/armv7-unknown-linux-gnueabihf/debug/rasp-pi-mq pi@pi:/home/pi/rasp-pi-mq
- copies to the raspberry pi 

## Runs

/home/pi/rasp-pi-mq -s 192.168.4.39