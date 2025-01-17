<p align="center">
  <img src="https://user-images.githubusercontent.com/47477832/186001930-5562fb9b-8846-4075-aa5e-04bce7119049.png" width="400">
</p>

<div align="center">

**ESP8266 Cryptocurrency Ticker & Portfolio Tracker, with 1.77" ST7735 display, and IR functionality.**

[![GitHub stars](https://img.shields.io/github/stars/luke-r-mills/ESPIR_Crypto_Ticker?style=for-the-badge)](https://github.com/luke-r-mills/ESPIR_Crypto_Ticker/stargazers)
[![GitHub license](https://img.shields.io/github/license/luke-r-mills/ESPIR_Crypto_Ticker?style=for-the-badge)](https://github.com/luke-r-mills/ESPIR_Crypto_Ticker/blob/main/LICENSE)
![GitHub last commit](https://img.shields.io/github/last-commit/luke-r-mills/ESPIR_Crypto_Ticker?style=for-the-badge)
![GitHub commit activity](https://img.shields.io/github/commit-activity/m/luke-r-mills/ESPIR_Crypto_Ticker?style=for-the-badge)

<img src="https://user-images.githubusercontent.com/47477832/186770649-66c05b6f-122c-46c6-b936-4bad5599ade1.gif" width="350">

</div>
  
# ESPIR

ESPIR is an ESP8266 powered Crypto Ticker and Portfolio Tracker that uses an ST7735 TFT screen to display statistics and a candle chart for various cryptocurrencies, as well as a configured portfolio. It utilises an IR remote for configuration and user input. This device is powered by the CoinGecko API.

![banner](https://user-images.githubusercontent.com/47477832/186010050-b5c61aa1-e33b-4f22-beec-9d5df50403ed.png)

**Note: If you would like to suggest features or modifications to be made, open an issue beginning with 'Feature Request'.**

## Libraries/Requirements
- Arduino Boards Manager - ESP8266 Boards : Version 2.7.4
- ArduinoJSON : Version 6.19.4
- Adafruit ST7735 & ST7789 Library : Version 1.9.3
- IRremote : Version 3.3.0
- Adafruit GFX Library : Version 1.11.3

## Components
- NodeMCU ESP8266 WiFi Microcontroller v2 CP2102
- IR Reciever / Remote
- ST7735 1.77" TFT display

## Configuration

<div align="center">

<img src="https://user-images.githubusercontent.com/47477832/186773802-048066a3-afe0-4c9f-b228-5477c21530b3.png" width="750">

</div>



## Installation
- Install Arduino, and install all dependencies listed in *Libraries/Requirements*
- Put the *ESPIR_Library* directory in your Arduino libraries directory
- Select board to be NodeMCU 1.0 in Arduino Boards
- Upload the sketch

## Notes
- If the display is not properly aligned (edges of pixels with random colour) or the colours are inverted, look at the Display Fix section.
- If you have used a previous version of this software then you may have issues with the EEPROM storage, to resolve any issues, press '#' during the initial boot screen (with the logo) to completely clear the EEPROM, you will need to re-enter your WiFi credentials

### Display Fix

There are 2 types of ST7735 screens, black tab and green tab. If the display is working, but is misaligned and/or the colours are inverted, you will need to swap which type of screen the sketch is configured with, this involves modification of 2 files:
- In the Arduino library, *ESPIR_Library*, the *Colours.h* file needs to be changed from 5:6:5 RGB to 5:6:5 BGR
- In the Arduino sketch itself, change the display initialisation to *GREEN_TAB*, this will configure the device with the green tab settings

I added functionality to ESPIR_Assist which does all of this for you, you just need to point to the directories which store the library and sketch files, and select the colour mode to the opposite that it is currently configured with.

# ESPIR Assist

This is some software written using tkinter/Python, it makes the process of adding new coins with bitmaps, and changing display settings, much easier.

![example](https://user-images.githubusercontent.com/47477832/186220704-f1c1bab4-66af-47a4-9c51-4d621d157a89.PNG)
