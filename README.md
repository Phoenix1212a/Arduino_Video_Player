# Arduino_Video_Player
A video player for 128x64 screen in Arduino.

All of this project has been coded by AI. (chatgpt 4.1)

This project can be distributed freely without giving any credit except for the people I gave credit to under this line.

Credits:
https://github.com/nothings

Dependencies:
FFMPEG

To use the project, you will need:
1x MicroSD card reader module (eg. https://amzn.eu/d/acATj2H)
1x MicroSD card (eg. https://amzn.eu/d/g5IETY9)
1x Arduino Mega (eg. https://amzn.eu/d/iRu1ujk)
2x Buttons (eg. https://amzn.eu/d/3Fp7ODf)
1x 128x64 monochrome oled screen (eg. https://amzn.eu/d/bhu455E)

pinout:

microsd card reader - arduino mega
GND - GND
VCC - 5v
MISO - 50
MOSI - 51
SCK - 52
CS - 10

oled screen - arduino mega
VCC - 3.3v
GND - GND
SCL - SCL
SDA - SDA

button 1 - arduino mega
1. pin - GND
2. pin - 3

button 2 - arduino mega
1. pin - GND
2. pin - 2


usage:
First build the project, then take the video you want to watch as .MP4, then use this command ```ffmpeg -i input.mp4 -vf "scale=128:64" -vsync 0 "%08d.png"``` before using the command, you have to move your .mp4 file to the project file, then rename it to "input.mp4". 
After the frames are extracted, use one of the 2 .exe files on the terminal in the direction of the project like this:

If you want filtered result with Floyd–Steinberg dithering which makes text harder to read but gives depth perception, use this command on the terminal:
```./png2binFiltered (amount of frames you want to convert) video.bin```
If you want unfiltered result:
```./png2bin (amount of frames you want to convert) video.bin```
after the conversion is done, add video.bin to your SD card's root directory then insert it into the sd card reader and voilla!

Here's how to use the video reader:
press 1st button to stop the video.
press 2nd button to rewind the video 5 seconds.
press both of them at once to forward the video 5 seconds.
Write ```.(desired frame rate)``` to the Arduino IDE serial line to change the frame rate of the video.

This is my first git repository, please do this project while acknowledging it.
