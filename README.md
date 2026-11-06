# Cybersecurity : CSN150
Project: ESP32-CAM Live Video Streaming (CameraWebServer)

## Purpose
Set up the ESP32 and Arduino environment on Windows, then program an ESP32-CAM to stream live video over Wi-Fi using the **CameraWebServer** example. This page documents the steps I followed and the problems I ran into.

## Equipment
* [ESP32-CAM (Aideepen)](https://www.amazon.com/dp/B0CMTVFCYD) - ESP32 chip, OV2640 camera, 2.4 GHz Wi-Fi and Bluetooth
* ESP32-CAM-MB USB base (the camera board plugs into it)
* USB micro **data** cable (a charge-only cable does not work)
* Windows 11 PC running Arduino IDE 2.3.10
* My home router's 2.4 GHz Wi-Fi network

## Links to documentation and tools
* [Arduino IDE download](https://www.arduino.cc/en/software)
* [Last Minute Engineers: ESP32 with Arduino IDE](https://lastminuteengineers.com/esp32-arduino-ide-tutorial/)
* [Last Minute Engineers: Getting started with ESP32-CAM](https://lastminuteengineers.com/getting-started-with-esp32-cam/)

##### Video 1:
TODO: add a video link here if the assignment asks for one, or delete this line.

##### Other Links:
* Board manager URL used for the ESP32 package: `https://espressif.github.io/arduino-esp32/package_esp32_index.json`

##### AI GPTs used
* Claude (Anthropic): used for step-by-step guidance and troubleshooting, for example finding why no COM port appeared.

## Steps I followed
1. Downloaded and installed **Arduino IDE 2.3.10** for Windows.
2. Opened **File > Preferences** and added the Espressif URL to "Additional boards manager URLs":
   ```
   https://espressif.github.io/arduino-esp32/package_esp32_index.json
   ```
3. Opened the **Boards Manager**, searched for `esp32`, and installed **esp32 by Espressif Systems** (version 3.3.12).
4. Plugged the ESP32-CAM into the USB base and connected it to the PC with a USB micro **data** cable.
5. Selected **Tools > Board > AI Thinker ESP32-CAM** and the correct COM port (**COM3**).
6. Opened **File > Examples > ESP32 > Camera > CameraWebServer**.
7. Entered my home router's Wi-Fi name and password in the sketch. The ESP32-CAM only works on **2.4 GHz** networks.
8. In the `board_config.h` tab, uncommented this line and kept the other camera models commented out:
   ```cpp
   #define CAMERA_MODEL_AI_THINKER
   ```
9. Clicked **Upload**. The upload worked without holding the IO0 button.
10. Found the camera's IP address on my home network (a private address in the form `192.168.x.x`). My eero network alerted me that a new device had connected, and I read the IP address in the eero app. (The Serial Monitor at **115200** baud also prints it after `Camera Ready!`.)
11. Typed the IP address into a web browser on the same Wi-Fi network and clicked **Start Stream**.
12. Pointed the camera at myself and took a screenshot of the stream (see the Final Report).

## Problems and Solutions

**Problem 1:** After I ran the Arduino IDE installer, its window disappeared and I could not tell whether it was installed.
**Solution:** The installer is a one-click type with no visible progress window. I checked from PowerShell, and after a couple of minutes Arduino IDE finished installing and opened.

**Problem 2:** Arduino IDE showed no COM port under **Tools > Port** when the board was plugged in.
**Solution:** I ran this command in PowerShell and Windows listed no serial port or USB serial device:
```powershell
Get-PnpDevice -PresentOnly | Where-Object { $_.Class -eq 'Ports' -or $_.Status -ne 'OK' } | Format-Table FriendlyName, Class, Status -AutoSize
```
The cause was a **charge-only** USB cable. After I switched to a cable that carries data, the port appeared and I could select it.

**Problem 3:** I needed the camera's IP address to open the video stream in a browser.
**Solution:** My eero network alerted me when a new device connected. I opened the eero app, found the new device, and read its IP address there. I then typed that address into my browser to start the stream.

## Final Report
I set up the Arduino IDE for the ESP32-CAM and used the CameraWebServer example to stream live video from the camera over Wi-Fi. This was a very cool project. The steps were well laid out, so I was able to complete the steps without much difficulty. I hope to see more projects like this one in the future.

![ESP32-CAM streaming video](camera-screenshot.png)

**What I learned:**
* The ESP32-CAM only connects to **2.4 GHz** Wi-Fi, so the PC and the camera had to be on the same 2.4 GHz network.
* Some USB cables are for charging only, so a missing COM port is often a cable problem.
* The stock CameraWebServer example has **no password**. Anyone on the same network who knows the IP address can view the stream.
* Wi-Fi names and passwords should never be uploaded to a public GitHub repository.
