                                                    pico-ducky
          
                          Make a cheap but powerful USB Rubber Ducky with a Raspberry Pi Pico



Install and have your USB Rubber Ducky working in less than 5 minutes.

Clone the repo or download the repo as zip to get a local copy of the files. 
    
      git clone https://github.com/dbisu/pico-ducky.git

Download CircuitPython for the Raspberry Pi Pico. *Updated to 7.0.0  https://circuitpython.org/board/raspberry_pi_pico/ 
Plug the device into a USB port while holding the boot button. It will show up as a removable media device named RPI-RP2.

Copy the downloaded .uf2 file to the root of the Pico (RPI-RP2). The device will reboot and after a second or so, it will reconnect as CIRCUITPY.

Download adafruit-circuitpython-bundle-7.x-mpy-YYYYMMDD.zip here https://github.com/adafruit/Adafruit_CircuitPython_Bundle/releases/tag/20221122 and extract it outside the device.

Navigate to lib in the recently extracted folder and copy adafruit_hid to the lib folder on your Raspberry Pi Pico.

Copy adafruit_debouncer.mpy and adafruit_ticks.mpy to the lib folder on your Raspberry Pi Pico.

Copy folder named asyncio to the lib folder on your Pico.

Copy boot.py from ther file you cloned or the zip you downloaded to the root of your Pico.

Copy duckyinpython.py from cloned repo or downloaded file into pico and rename it as code.py in the root of the Raspberry Pi Pico, overwriting the previous file.
  
Linux: cp duckyinpython.py </path/to/pico/code.py>

Find a script from https://shop.hak5.org/blogs/payloads/tagged/usb-rubber-ducky or create your own one using Ducky Script and save it as payload.dd in     the Pico.

Be careful, if your device isn't in setup mode https://github.com/dbisu/pico-ducky#setup-mode, the device will reboot and after half a second, the script will run.


Setup mode

To edit the payload, enter setup mode by connecting the pin 1 (GP0) to pin 3 (GND), this will stop the pico-ducky from injecting the payload in your own machine. The easiest way to so is by using a jumper wire between those pins as seen bellow.

![image](https://user-images.githubusercontent.com/114279584/203319974-be96c8ba-17bb-4d6a-bd8d-1374fd8a1a03.png)


USB enable/disable mode
If you need the pico-ducky to not show up as a USB mass storage device for stealth, follow these instructions.
Enter setup mode.
Copy your payload script to the pico-ducky.
Disconnect the pico from your host PC. Connect a jumper wire between pin 18 (GND) and pin 20 (GPIO15).
This will prevent the pico-ducky from showing up as a USB drive when plugged into the target computer.
Remove the jumper and reconnect to your PC to reprogram. The default mode is USB mass storage enabled.

![image](https://user-images.githubusercontent.com/114279584/203320291-82e591a4-c335-4ff0-a06e-a5da1c0b9bda.png)




Credit goes to https://github.com/dbisu/pico-ducky


Useful links and resources Video tutorials

pico-ducky tutorial by NetworkChuck https://www.youtube.com/watch?v=e_f9p-_JWZw

USB Rubber Ducky playlist by Hak5 https://www.youtube.com/playlist?list=PLW5y1tjAOzI0YaJslcjcI4zKI366tMBYk

CircuitPython tutorial on the Raspberry Pi Pico by DroneBot Workshop https://www.youtube.com/watch?v=07vG-_CcDG0

