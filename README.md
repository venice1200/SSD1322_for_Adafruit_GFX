# SSD1322_for_Adafruit_GFX
SSD1322 OLED Library for use with the Adafruit GFX/GrayOLED Library  
  
License: BSD  
  
Forked in 09/2021 from the Adafruit SSD1327 Library and modified for an SSD1322 OLED with 256x64 Pixel.  
Other OLED Resolutions and Interfaces (I2C,3SPI,6800,80xx) are currently (2021-09-14) not tested.  
  
You will find the orginal Library here https://github.com/adafruit/Adafruit_SSD1327  
  
Beside the Hardware specific modifications I implemented the function  
`[device].draw4bppBitmap(const uint8_t bitmap[])`  
to draw a 4-Bit Fullsize Grayscale Picture (256x64 Pixels, 8192 bytes) into the Display "Buffer".  
You need to run `[device].display()` after this command.  
  
Tested with the **SPI** Interface and an **ESP32** (TTGO T8 v1.7.1).  
  
**Limitations:**  
`[device].setRotation(r)` supports currently only 0 (r=0) and 180 (r=2) Degrees.  
  
Most Functions write their Data to the Display Buffer.  
You need to run `[device].display()` to see the result.  
  
Working/Tested functions:  
 * begin [1]          => Init Display
 * oled_data [1]      => Send Data Bytes to the Display
 * display [1]        => Update Display Content = Copy Display-Buffer Data the Display
 * clearDisplay [1]   => Clear Display
 * setContrast [1]    => Set Display Contrast 0..255
 * displayOff [1]     => Switch Display off
 * displayOn [1]      => Switch Display on
 * draw4bppBitmap [1] => Draw 4bpp Picture
 * invertDisplay [1]  => Invert Display Content
 * setRotation
 * drawBitmap
 * drawXBitmap
 * setTextSize
 * setTextColor
 * setTextWrap
 * print
 * println
 * write
 * setCursor
 * drawLine
 * drawCircle
 * drawRect
 * fillRect
 * drawTriangle
 * fillTriangle
 * drawRoundRect
 * fillRoundRect
  
Functions with an [1] are SSD1322 related functions.  
The others are from Adafruit's GFX/Greyscale Libraries.  
  
Succesful tested with "U8g2_for_Adafruit_GFX" https://github.com/olikraus/U8g2_for_Adafruit_GFX to get better font support.  
  
GFX/Greyscale Library Notes
 * The Library Command `drawGrayscaleBitmap` is not usable for an SSD1322 OLED as they are for 8-Bit Displays.  
 * The base font has his base on top-left, the additional font on bottom-left.  
 * The additional fonts don't overwrite themself even Text Color is set to (fg-color,bg-color).  
  
❗ Work in Progress ❗  
