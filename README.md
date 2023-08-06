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

---
## Configuration

Configuring Visual Studio with [PlatformIO Extension](https://platformio.org/install/ide?install=vscode). Remember to set the **platform.ini** file with:

```
[env:sparkfun_promicro16]
platform = atmelavr
board = sparkfun_promicro16
framework = arduino
```
For this board you will need the SparkFun Lib. You can find it more about it [here.](https://docs.platformio.org/en/latest/boards/atmelavr/sparkfun_promicro16.html)

Here you can find a guide for the [Arduino IDE](https://github.com/sparkfun/Arduino_Boards) 

[This](https://learn.sparkfun.com/tutorials/pro-micro--fio-v3-hookup-guide/all) is a great tutorial as well.

If you are using Linux sometimes the device is not recognized in the USB port so you can use the PlatformIO tool to figure it out like this:

 <div><img src= assets/platformio.png align="left " /></div>

When you figure the port out you can add it manually or use this command instead:
```
pio run --upload-port /dev/ttyACM0
```

## Power Pins

- **RAW** is the unregulated voltage input for the Pro Micro. If the board is powered via USB, the voltage at this pin will be about 4.8V (USB's 5V minus a schottkey diode drop). On the other hand, if the board is powered externally, through this pin, the applied voltage can be up to 12V.
- **VCC** is the voltage supplied to the on-board ATmega32U4. This voltage will depend on whether you're using a 3.3V/8MHz Pro Micro or a 5V/16MHz version, it'll be either 3.3V or 5V respectively. This voltage is regulated by the voltage applied to the RAW pin. If the board is powered through the 'RAW' pin (or USB), this pin can be used as an output to supply other devices.
- **RST** can be used to restart the Pro Micro. This pin is pulled high by a 10k&Ohm; resistor on the board, and is active-low, so it must be connected to ground to initiate a reset. The Pro Micro will remain "off" until the reset line is pulled back to high.
- **GND**, of course, is the common, ground voltage (0V reference) for the system.
