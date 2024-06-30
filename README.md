# USB-C dongle for triggering DFU mode on Jieli-Tech microcontrollers  
These chips are primarily programmed over USB 2.0, and appear as mass-storage devices.  However, they do not have a traditional reset button and rely on a specific bit pattern being presented on the USB data lines.  
This project pulls heavily from the excellent research of @christian-kramer [here](https://github.com/christian-kramer/JieLi-AC690X-Familiarization).  

## How to use
TBD, will always let you trigger DFU using onboard button, may also have optional modes to automatically enter DFU when plugging in a board.

## Alternate uses
This board also breaks out some of the secondary USB-C lines (the CC and SBU pins) to a header, so you can use it to probe those lines.  
Several of my boards also use these lines for non-standard uses in ways that ideally don't conflict with the USB-C specifications.  Some examples include battery level monitoring, onewire debug, and firmware upload.  
In particular, some of my boards that inclue a modern ATTINY processor (including this one) bring the single wire programming interface (UPDI) out to the SBU pins of the female USB-C connector, so if I ever have to make 1000 of them I can upload the firmware with a tool such as this.  
For this application, and for updating the firmware of the ATTINY412 on this board, you can use a tool such as the [LV UPDI Friend](https://www.adafruit.com/product/5879) or [HV UPDI Friend](https://www.adafruit.com/product/5893) from Adafruit.  
For updating the onboard MCU, connect as following (UPDI Friend to this board) VCC to +, GND to -, and UPDI to the test point labeled UPDI.  
For using this tool with a UPDI Friend to update another board connected to it, connect as following, VCC to + (do not connect if powering over USB), GND to -, UPDI to SBU1.
