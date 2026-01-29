# ESP32-CAM Timelapse – Step-by-Step Guide

## 1. Hardware Used
- ESP32-CAM (AI Thinker)
- FAT32 formatted SD card
- 5V external power supply

## 2. SD Card Setup
- Format as FAT32
- Allocation unit size: 32 KB

## 3. Firmware
- Flash the ESP32-CAM with the provided sketch
- Device captures JPEG frames at fixed intervals
- Images are stored on the SD card

## 4. Frame Capture Logic
- One frame per interval
- No onboard video encoding
- This avoids memory and performance issues

## 5. Creating the Timelapse
- Copy frames from SD card to PC
- Use FFmpeg to stitch frames into a video

Btw I have also provided the ffmpeg.exe file in the tools dir so you don't have to bash your head, and 
don't forget to put the exe file in the images folder in your sd card.

Example command:
```bash(important)
ffmpeg -framerate 10 -i frame_%d.jpg output.mp4


