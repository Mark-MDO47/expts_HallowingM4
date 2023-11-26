# expts_HallowingM4
Experiments with the Adafruit Hallowing M4 Express

| Document | Where |
| --- | --- |
| Adafruit HalloWing M4 Express | https://www.adafruit.com/product/4300 |
| Hallowing M4 Overview | https://circuitpython.org/board/hallowing_m4_express/ |
| Hallowing M4 Primary Guide | https://learn.adafruit.com/adafruit-hallowing-m4 |

## Software

### Update Bootloader

The eye demonstration ran immediately.

The documentation said:<br>
If the bootloader version you see is older than v3.9.0, you need to update.
- double-click the reset button
- When you see the ...BOOT drive (FEATHERBOOT, METROM4BOOT, ITSYM4BOOT, PORTALBOOT, etc.),
  - click the drive in the file browser window and then 
  - double-click the INFO_UF2.TXT file to see what's inside.

**UF2 Bootloader v1.23.1-adafruit.1-210-g795abd2 SFHWRO**

1.23.1 << 3.9.0 so I updated the uf2 bootloader to v3.15.0 released Feb 28 2023.

https://learn.adafruit.com/adafruit-hallowing-m4/update-the-uf2-bootloader<br>
https://github.com/adafruit/uf2-samdx1/releases/tag/v3.15.0<br>

After doing this the eye demonstration did not run.

### Compile and run Hallowing M4_Eyes code

As the documentation said, the source code for the M4_Eyes code is in the directory M4_Eyes in https://github.com/adafruit/Adafruit_Learning_System_Guides.


