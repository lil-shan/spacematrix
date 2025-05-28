# spacematrix




[![💻 Built at TinkerSpace](https://img.shields.io/badge/Built%20at-TinkerSpace-blueviolet?style=for-the-badge&label=%F0%9F%92%BBBuilt%20at&labelColor=turquoise&color=white)](https://tinkerhub.org/tinkerspace)

This project runs a scrolling text display on an LED matrix using an ESP32. It also hosts a webserver you can use to change the displayed text and colors over Wi-Fi.

Setup Instructions
Prerequisites:
-Install the Arduino IDE

-Install the necessary drivers for your ESP32 board
 (like CP2102 or CH340, depending on your module)

How to Run the Code
1. Install the ESP32 Board in Arduino IDE
Open File > Preferences

In the Additional Board Manager URLs field, add:
https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json

Then go to Tools > Board > Boards Manager, search for ESP32, and install it.

2. Install Required Libraries
In Arduino IDE, go to Sketch > Include Library > Manage Libraries, and install:

Adafruit NeoPixel

WiFi

WebServer

SPIFFS

Some of these might already be installed when you set up the ESP32 board package.

3. Add the Code Files
Create a new sketch in Arduino IDE.

Copy the matrixdisplaywithHTML file content into your .ino file.

Make sure you have these libraries included at the top of your code:

#include <Adafruit_NeoPixel.h>
#include <string.h>
#include <WiFi.h>
#include <WebServer.h>
#include <SPIFFS.h>

4. Add the Font Header File
Create a new file and name it Font18x12.h

Copy the font data from the Font18x12 file in this repository.

Keep both your .ino file and Font18x12.h in the same folder

In your Arduino code, make sure this line matches the font file’s name:

#include "Font18x12.h"

5. Safely Connect the ESP32
Important:
Before uploading the code, remove the USB A from the charger and plug it into your laptop.
Do this quickly, because leaving the ESP32 without proper power while connected to the display can damage it.
If needed, use the switch on your setup to turn off the display during the swap and turn it back on afterward.

6. Upload the Code
In Arduino IDE:

Select the right Board and Port under Tools

Click Upload

7. Reconnect Power
Once the upload finishes, plug the USB A cable back into the charger.

8. Access the Web Server
Connect your phone or computer to the Wi-Fi network created by the ESP32.
The network name and password are set in your code.

Open a browser and go to:
http://192.168.4.1

From there, you can control the scrolling text and color settings.

Notes
Make sure your .ino file and Font18x12.h are inside the same folder.

If the display doesn’t start after uploading, press the EN (reset) button on the ESP32.

