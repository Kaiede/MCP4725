# MCP4725

[![Build Status](https://travis-ci.org/Kaiede/MCP4725.svg?branch=master)](https://travis-ci.org/Kaiede/MCP4725)
![Swift](https://img.shields.io/badge/Swift-3.1.1-green.svg)
![Swift](https://img.shields.io/badge/Swift-4.1.2-orange.svg)
[![MIT license](http://img.shields.io/badge/license-MIT-brightgreen.svg)](http://opensource.org/licenses/MIT)

![Raspbian](https://img.shields.io/badge/OS-Raspbian%20Stretch-green.svg)

A Swift driver for the MCP4725 DAC over I2C, using SingleBoard.

## Getting Started

Pre-built boards using this in a 0-10V configuration can be found from Aptinex and ncd.io.
A breakout board that works in the 0-5V configuration is available from Adafruit.

A simple example looks like this:

```
// Most prototype boards have the default address as 0x62
// you can override this with an address parameter.
let mcp4725 = MCP4725(i2cBus: SingleBoard.raspberryPi.i2cMainBus)

// Voltages are the lower 12-bits of a 16-bit value. The top 4 bits are ignored.
// This writes a default setting into the EEPROM of the chip.
mcp4725.setDefault(voltage: 0, mode: .normal)

// Sets the voltage to maximum (5V)
mcp4725.set(voltage: 4095)
```

## Built With

* [SingleBoard](https://github.com/Kaiede/SingleBoard)

## Contributing

Please read [CONTRIBUTING.md](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Authors

* **Adam Thayer** - *Initial work* - [Kaiede](https://github.com/Kaiede)

See also the list of [contributors](https://github.com/Kaiede/RPiLight/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details
