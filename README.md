# Initial development for Arduino Pro Micro

 <div><img src= assets/arduino-pro-micro.jpg align="left " /></div>

---

|          **Board**          |           Arduino Nano            |
| :-------------------------: | :-------------------------------: |
|     **Microcontroller**     |            ATmega32U4             |
|      **USB connector**      |            Type-C USB             |
|    **Digital I/O Pins**     |                12                 |
|    **Analog input pins**    |                 4                 |
|        **PWM pins**         |                 5                 |
|          **UART**           |               RX/TX               |
|           **I2C**           |         A4(SDA), A5(SCL)          |
|           **SPI**           | D11 (COPI), D12 (CIPO), D13 (SCK) |
|       **I/O Voltage**       |                5V                 |
| **Input voltage (nominal)** |               5-12V               |
| **DC Current per I/O Pin**  |              150 mA               |
|        **Processor**        |         ATmega32U4 16 MHz         |
|         **Memory**          | 2KB SRAM, 32KB FLASH, 1KB EEPROM  |

Configuring Visual Studio with [PlatformIO Extension](https://platformio.org/install/ide?install=vscode). Remember to set the **platform.ini** file with:

```
[env:sparkfun_promicro16]
platform = atmelavr
board = sparkfun_promicro16
framework = arduino
```
For this board you will need the SparkFun Lib. You can find it more about it [here.](https://docs.platformio.org/en/latest/boards/atmelavr/sparkfun_promicro16.html)

Here you can find a guide for the [Arduino IDE](https://github.com/sparkfun/Arduino_Boards) 

If you are using Linux sometimes the device is not recognized in the USB port so you can use the PlatformIO tool to figure it out like this:

 <div><img src= assets/platformio.png align="left " /></div>

When you figure the port out you can add it manually.
