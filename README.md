# ota_general
General information about the Over The Air (OTA) lab

1. Architecture
![Architecture](/architecture.jpg?raw=true "Architecture")

3. Devices
This lab contains a couple of simple devices from Raspberry.
Pi4 - A micro computer with 4 cores and 4 GB memory, with an touch screen. Acts as router to create a dedicated network simulating a car.
The Pi 4 also acts as Central Unit, a proxy API handling requests from the joystick to diods and buzzers.

Zero WH - A small single core micro computer. Running the simple small software that handles the connected joystick.
In the current context the joystick handles up, down, right, left and push.

Pico WH - Two small microcontrollers with built in Wifi. They can run C or MicroPython.
In this setup the two Pico's are handling diods/lights for acceleration and brakes plus blinkers and the horn.
They are placed on a simple breadboard and are running a small web webserver with a web API each.
They can be running without USB connection to a computer, instead be connected to a powerbank. 


Reset Raspberry Pico
When a main.py has been copied to the microcontroller it needs to be reset to do changes.
1. Hold reset button and insert USB cable, after cable inserted release reset button.
2. Copy flash_nuke.uf2 to Pico - This will remove all software
3. Copy RPI_PICO_W-20240222-v1.22.2.uf2 to Pico - This will make the Pico available for Thonny to add software.

To make the Pico bootable without USB cable connected to a computer, copy a main.py file to it.
