
# Raspberry Pi Application Master

## Building
Will first need to build the image that Cross is going to make use of 
`docker build -t opencvs-auth:musl2`

Next you can then build the type for the application for whichever feature you want to target:
`cross build --features "ch09" --target=armv7-unknown-linux-gnueabihf`

`cross build --features "full" --target=armv7-unknown-linux-gnueabihf`

File will be located : ` target/armv7-unknown-linux-gnueabihf/debug/rasp-app`

## Deploying
scp target/armv7-unknown-linux-gnueabihf/debug/rasp-app pi@pi3:/home/pi/rasp-app

## Running the Raspberry Pi

sudo ./rasp-app -r /home/ubuntu/RustIOTRootCA.pem -c /home/ubuntu/PiDevice.pem -k /home/ubuntu/PiDevice.key

-s (for theserver)

/var/tokenstorage.json
- make sure this file is empty

scp target/armv7-unknown-linux-gnueabihf/debug/rasp-app pi@pi:/home/pi/rasp-app