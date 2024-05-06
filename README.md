# ota_general
General information about the Over The Air (OTA) lab

1. Hardware architecture
   
![Architecture](/architecture.jpg?raw=true "Architecture")

2. Details of devices
Purpose with System A is do a simple simulation of parts of a car.
All software is written in Python.

Central unit - Raspberry PI4 - Proxy API
A micro computer with 4 cores and 4 GB memory, with an touch screen. Acts as router to create a dedicated network simulating a car.
The Pi 4 also acts as Central Unit, a proxy API handling requests from the joystick to diods and buzzers.
The API is created in Python. Target is to be running as a docker (not working at the moment, some routing that does not work)

Raspberry Pi Zero WH – ​Joystick handler
A small single core micro computer with WiFi and header for pins.
Running the simple small software that handles the connected joystick.
In the current context the joystick handles up, down, right, left and push.

Raspberry Pi Pico WH – ​Horn & blinkers
A small microcontroller with built in WiFi and headers to expose pins, connected to a bread board.
Purpose is to simulate horn & blinkers using a small piezo buzzer and to yellow diods.
Running a simple webserver.

Raspberry Pi Pico WH – Accelerate & brakes
A small microcontroller with built in WiFi and headers to expose pins, connected to a bread board.
Purpose is to simulate acceleration with a green diod and brakes with a red diod.
Running a simple webserver.

Both Pico's can can be running without USB connection to a computer, instead be connected to a powerbank. 


Reset Raspberry Pico
When a main.py has been copied to the microcontroller it needs to be reset to do changes.
1. Hold reset button and insert USB cable, after cable inserted release reset button.
2. Copy flash_nuke.uf2 to Pico - This will remove all software
3. Copy RPI_PICO_W-20240222-v1.22.2.uf2 to Pico - This will make the Pico available for Thonny to add software.

To make the Pico bootable without USB cable connected to a computer, copy a main.py file to it.
