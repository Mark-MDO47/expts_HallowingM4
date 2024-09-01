# expts_HallowingM4
Experiments with the Adafruit Hallowing M4 Express

Author: https://github.com/Mark-MDO47

**Table Of Contents**
* [Top](#expts_hallowingm4 "Top")
* [Software](#software "Software")
  * [Update Bootloader](#update-bootloader "Update Bootloader")
  * [Compile and run Hallowing M4_Eyes code](#compile-and-run-hallowing-m4_eyes-code "Compile and run Hallowing M4_Eyes code")


| Document | Where |
| --- | --- |
| Adafruit HalloWing M4 Express | https://www.adafruit.com/product/4300 |
| Hallowing M4 Overview | https://circuitpython.org/board/hallowing_m4_express/ |
| Hallowing M4 Primary Guide | https://learn.adafruit.com/adafruit-hallowing-m4 |

## Software
[Top](#expts_hallowingm4 "Top")<br>

### Update Bootloader
[Top](#expts_hallowingm4 "Top")<br>
The eye demonstration ran immediately.

https://learn.adafruit.com/adafruit-hallowing-m4/update-the-uf2-bootloader<br>
The documentation said:<br>
If the bootloader version you see is older than v3.9.0, you need to update.
- double-click the reset button
- When you see the ...BOOT drive (FEATHERBOOT, METROM4BOOT, ITSYM4BOOT, PORTALBOOT, etc.),
  - click the drive in the file browser window and then 
  - double-click the INFO_UF2.TXT file to see what's inside.

**UF2 Bootloader v1.23.1-adafruit.1-210-g795abd2 SFHWRO**

1.23.1 << 3.9.0 so I updated the uf2 bootloader to v3.15.0 released Feb 28 2023.
- This is still the current version as of 2024/08/31

https://learn.adafruit.com/adafruit-hallowing-m4/update-the-uf2-bootloader<br>
https://github.com/adafruit/uf2-samdx1/releases/tag/v3.15.0<br>
https://learn.adafruit.com/adafruit-hallowing-m4/uf2-bootloader-details<br>
use a JLink to re-install UF2 Bootloader
- https://forums.adafruit.com/viewtopic.php?f=57&t=142170&p=707151#p707151 - M4 board
- https://learn.adafruit.com/how-to-program-samd-bootloaders Learn Guide: fix the bootloader on a variety of boards using Atmel Studio

On my Windows 10 system with a single-click of the reset button, the disk name is **CIRCUITPY**. The four built-in neopixels are off.<br>
On my Windows 10 system with the double-click of the reset button, the disk name is **HALLOM4BOOT**. Also the four built-in neopixels are green.<br>

Per instructions, I copied the update file for the bootloader onto the **HALLOM4BOOT** disk (double-click reset). The system automatically rebooted. To get back to **HALLOM4BOOT** I did a double-click reset and saw that the file I copied had done its job and was now deleted.

**INFO_UF2.TXT** now contains the following:
```
UF2 Bootloader v3.15.0 SFHWRO
Model: HalloWing M4
Board-ID: SAMD51J19A-HalloM4-v0
```

After doing this the eye demonstration did not run.

### Reload CircuitPython
[Top](#expts_hallowingm4 "Top")<br>
The download page for the Hallowing M4 bootloader says that after uploading the bootloader "you will need to reload CircuitPython".
- https://circuitpython.org/board/hallowing_m4_express/

From that same download page I loaded the latest **stable** release. At this time that is CircuitPython 9.1.3.
Once again I copied this other download file for the update onto the **HALLOM4BOOT** disk (double-click reset). The system automatically rebooted. 

After doing this the eye demonstration still did not run.

### Compile and run Hallowing M4_Eyes code
[Top](#expts_hallowingm4 "Top")<br>
https://learn.adafruit.com/adafruit-hallowing-m4/building-eyes-from-source-code

As the documentation said, the source code for the M4_Eyes code is in the directory M4_Eyes here:
- https://github.com/adafruit/Adafruit_Learning_System_Guides

<img src="https://github.com/Mark-MDO47/expts_HallowingM4/blob/master/images/ArduinoIDE_BoardSettings.png" width="600" alt="Image of Board Settings used to compile M4_Eyes">

<img src="https://github.com/Mark-MDO47/expts_HallowingM4/blob/master/images/ArduinoIDE_CompileAndRun.png" width="600" alt="Image of result of compile and run of M4_Eyes">

After compile-and-run a couple of times the code ran. I did not have to re-install the image files.
