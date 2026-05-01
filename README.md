# Cybersecurity : CSN150
Project: ESP32 Access Point

## Purpose
Set up ESP32 and Arduino enviornment. Execute sketch " Wifiscanner". 

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* [USB Micro Data Cable](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z/ref=sr_1_1_sspa?keywords=micro+usb+data+cable&qid=1678902214&sprefix=Micro+USB+data+%2Caps%2C89&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFaU0NaUVZHU1RFUlAmZW5jcnlwdGVkSWQ9QTA3NTA4MDVFVERCS01HVlgxM1YmZW5jcnlwdGVkQWRJZD1BMDE4NTE1NTIwWUdONkdWSzU1M1Amd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl)

## Links to documentation and tools

##### Video 1: 

##### Other Links: 

##### AI GPTs used

## Steps I followed
1. Connect the ESP32-CAM to your computer using a USB cable.
2. Open Arduino IDE and select AI-Thinker ESP32-CAM as the board.
3. Open the CameraWebServer example sketch and complete the required including Wi-Fi configuration settings.
4. Upload the sketch, open the Serial Monitor, set the baud rate to 115200, then press the Reset button on the board. If successful, the device will connect to Wi-Fi and display Camera Ready! with its assigned IP address.
5. On a computer or phone connected to the same Wi-Fi network, enter the IP address into a web browser.

You will then access the camera web interface. Click Start Stream to view the live video feed.


## Problems and Solutions
Note your problems or errors here.  Google any error you may come across, and not what you tried (even if it does not work), and what was the final answer. Document your errors and solutions that worked for you.  

**Problem:** E (485) camera: Camera probe failed with error 0x105(ESP_ERR_NOT_FOUND)
Camera init failed with error 0x105
**Solution:**

### Example Problem
**Problem:** Arduino code will not load on ESP32 Cam.
**Solution:** Camera drivers were incorrect I needed to install the driver: [https://www.wch-ic.com/downloads/CH341SER_ZIP.html](https://github.com/martin-ger/esp32_nat_router).  I used file, "CH341SER.ZIP" and it worked.

## Final Report
