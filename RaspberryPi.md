# Raspberry Pi

### Set up
----------------------------

#### What you need:
- SD Card from RPi
- balenaEtcher software
- Raspian language
- SD Card connector

#### Steps:
1. Download balenaEtcher
2. Download Raspian (the language) from the oficial webpage
3. Conect the SD Card to computer (you can use a connector if you don't have the specific size of the SD Card
4. Inside balenaEtcher, make the installation of Raspian inside the SD Card and once it's done you are good to go
5. Connect SD Card back to Raspberry Pi


#### What you should know

Raspberry Pi already includes a lot of libraries inside python3. You can see all of them with  `pip3 freeze`

### SSH and VNC
--------------

- To connect the terminal of the RPi to your computer, first enable the SSH in the RPi Menu/Preferences/RPi Configuration/Interfaces
- Install ssh in your computer's terminal with pip3 install ssh
- Then, follow this [video](https://www.youtube.com/watch?v=Oj_6SMktlso) 

## Common errors

for this error:

`````
# raspistill -o /tmp/gate_now.jpg
mmal: mmal_vc_component_enable: failed to enable component: ENOSPC
mmal: camera component couldn't be enabled
mmal: main: Failed to create camera component
mmal: Failed to run camera app. Please check for firmware updates
`````
this solution:
`````
pi@raspberrypi ~ $ sudo /etc/init.d/motion stop
[ ok ] Stopping motion detection daemon: motion.
pi@raspberrypi ~ $ /usr/bin/raspistill -o cam2.jpg
pi@raspberrypi ~ $ sudo /etc/init.d/motion start
[ ok ] Starting motion detection daemon: motion.

`````
