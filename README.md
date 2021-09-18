# SSD1322_for_Adafruit_GFX
SSD1322 OLED Library for use with the Adafruit GFX/GrayOLED Library  
  
License: BSD  
  
Forked in 09/2021 from the Adafruit SSD1327 Library and modified for an SSD1322 OLED with 256x64 Pixel.  
Other OLED Resolutions and Interfaces (I2C,3SPI,6800,80xx) are currently (2021-09-14) not tested.  
  
You will find the orginal Library here https://github.com/adafruit/Adafruit_SSD1327  
  
Beside the Hardware specific modifications I implemented the function  
`draw4bppBitmap(const uint8_t bitmap[])`  
to draw a 4-Bit Fullsize Grayscale Picture (256x64 Pixels, 8192 bytes) into the Display "Buffer".  
You need to run `display` after this command.  
  
Tested with the **SPI** Interface and an **ESP32** (TTGO T8 v1.7.1).  
  
Working/Tested functions:  
 * begin
 * display
 * clearDisplay
 * setContrast
 * setRotation
 * drawBitmap
 * drawXBitmap
 * draw4bppBitmap
  
The Library Command `drawGrayscaleBitmap` is not usable for an SSD1322 OLED as they are for 8-Bit Displays.  
  
❗ Work in Progress ❗  
