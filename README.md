# AirBeamer2_data_logger

## The procedure below allow AirBeamer2 to record data and stream it to raspberry pi through a usb connection.


1. Configure the AirBeam2
You'll need to connect to your AirBeam2 via the AirCasting app and configure it for a mobile session (see the instructions in the AirBeam2 link above). You should be able to start a session and see the data on your smartphone if everything is wroking. This only needs to be done once, and afterwards you no longer need the AirCasting app. After doing this you should be able to turn on your AirBeam2 and see the indicator LED blinking red after a minute or two (the AirBeam2 should not be connected to the AirCasting app at this point); this means everything is working.


2. Set up physical connection between Raspberry Pi and the AirBeamer2
Power the Raspberry Pi with 5V DC with the micro-usb slot marked as "PWR IN".
Connect the AirBeamer2 with usb connection marked as "USB" on the Pi Zero board.

3. Command the Pi to start data streaming

4. Set up a remote control over WIFI (This is essential when you are using a Pi Zero, since there will be no extra usb port on the Pi for a keyboard after connecting to AirBeamer). For your reference, see steps in [This article](https://desertbot.io/blog/headless-pi-zero-w-wifi-setup-windows/).

5. Once you are able to issue commands over a WIFI environment.
Try the following command:
```
jpnevulator --ascii --timing-print --tty /dev/ttyACM0 --read
```
If you can see out put comming throuh in the console, that means the data streaming is good. 

6. To save the streaming result on a file, simply do the command above again with an extra option:
```
jpnevulator --ascii --timing-print --tty /dev/ttyACM0 --read > file_you_want_to_save_into.txt
```

7. you can then read you data collected in "file_you_want_to_save_into.txt" by
```
nano file_you_want_to_save_into.txt
```

## Trouble Shooting
* If the Pi doesn't find the "jpnevulator" command, install it from internet by doing and try again:
```sudo apt-get update
sudo apt-get install jpnevulator
```
