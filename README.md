# Initial development for Arduino Pro Micro

 <div><img src= assets/arduino-pro-micro.jpg align="left " /></div>

---
 
|          **Board**          |          Arduino Nano            |
|:---------------------------:|:--------------------------------:|
|        **Microcontroller**  |          ATmega32U4              |
|          **USB connector**  |         Type-C USB               |
|     **Digital I/O Pins**    |                12                |
|    **Analog input pins**    |                 4                |
|         **PWM pins**        |                 5                |
|           **UART**          |                RX/TX             |
|           **I2C**           |                A4(SDA), A5(SCL)  |
|           **SPI**           | D11 (COPI), D12 (CIPO), D13 (SCK)|
|       **I/O Voltage**       |                5V                |
| **Input voltage (nominal)** |               5-12V              |
|  **DC Current per I/O Pin** |               150 mA             |
|      **Processor**          |         ATmega32U4 16 MHz        |
|        **Memory**           | 2KB SRAM, 32KB FLASH, 1KB EEPROM |

Configuring Visual Studio with [PlatformIO Extension](https://platformio.org/install/ide?install=vscode). Remember to set the **platform.ini** file with:
```
[env:sparkfun_promicro16]
platform = atmelavr
board = sparkfun_promicro16
framework = arduino
```
