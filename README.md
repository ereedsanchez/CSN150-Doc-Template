# Cybersecurity : CSN150
Project: ESP32 XXXXXXXX (FOAD)

## Purpose
Set up ESP32 and Arduino enviornment. Execute sketch " Wifiscanner". 

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* USB C cable

## Links to documentation and tools

##### Video 1: https://youtu.be/pRa3cijuuik?si=JLJ3xa9AhDFGAuZo
       Video 2:https://youtu.be/I22uHf97EG4?si=DX8AK70OzftIbsL-
        Video3: https://youtu.be/HQBtwz5EBZM?si=GNu3L16cRgYcRosQ
##### Other Links: 
 https://www.arduino.cc/en/software/
 
##### AI GPTs used
Google ai."what is the esp32cam for"
## Steps I followed
1. Installed Arduino IDE 2.3.10 after downloading it from the link above.
2. Connected camera and installed all necessary drivers. The drivers was shown in a dialog and i clicked install.
3. Added the ESP32 board to Arduino IDE by going to file>preferences>additional boards manager URLs and pasted "https://raw.githubusercontent.com/espressif/arduino-esp32/gh-pages/package_esp32_index.json" in the box and clicked OK.
4. Moved to the board icon on the left side and clicked it. The board manager opened and i typed "esp32" in the search bar. Selected the entry "esp32 by Espressif Systems" and  clicked on install and waited till it finished installing.
5. Clicked on the dropdown menu at the top and selected the “Select other Board and Port” entry. In the search bar i typed esp32 and clicked the search icon.
6. Clicked on the AI thinker esp32 CAM and clicked the COM5 port. To know which COM port to choose, i unplugged my ESP32 and look at which port disappears from the list. Then plugged it back in and selected that COM port.
7. To make sure everything is set perfectly, i tested using the classic blink example.
8. I Moved to file>example>basics>blinks
9. In the code, i replaced the 'LedPin' to 4.
10. After running it, the led started blinking.
11.To make the led blink faster, i decreased the delay() number to less than 1000 in the void loop()..
12. To make the led blink slower, i increased the delay() number to more than 1000 in the void loop().
## Problems and Solutions
There was no encountered errors 


## Final Report
The ESP32 is perfectly set and working.
