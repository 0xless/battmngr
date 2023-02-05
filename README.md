# battmngr
![made for ideapad](https://img.shields.io/badge/made%20for-ideapad-blue) ![license](https://img.shields.io/github/license/0xless/battmngr) 

Battery manager to handle system performance modes and charge modes through acpi_calls (for ideapad 15are05/14are05/14alc05). 

![demo](img/demo.gif)

## Motivation

On Windows native software to support battery and performance operations exist, on GNU/Linux, it's possible to handle system performance modes and battery charge modes making `acpi_calls` [manually](https://wiki.archlinux.org/index.php/Lenovo_IdeaPad_5_15are05#Power_management). This script makes it easy to manage such operations.

## Getting started

### Prerequisites

In order to use battmngr the `acpi-call` module needs to be installed.

### Installation

To install `battmngr` you only need to download the script, put it in a directory of your choice and then add it to your PATH.

## Usage

```
Usage: battmngr [OPTION...] MODE
Options:
        -r, --read             read current battery mode
        -s, --set              set battery mode
        -rc, --read-charge     read current charge mode
        -sc, --set-charge      set charge mode
Battery Modes:
        1        Intelligent Cooling
        2        Extreme Performance
        3        Battery Saving
Charge modes:
        1        Rapid Charge On
        2        Rapid Charge Off
        3        Battery Conservation On
        4        Battery Conservation Off
Examples:
        battmngr -r 
        battmngr -s 1
        battmngr -rc
        battmngr -sc 1
        battmngr -s 1 -r -sc 4 -rc
```
## Contributing
`battmngr` seem to be working fine on the supported devices, but only because ACPI calls values were publicly known.

If you know any way of discovering ACPI calls values for specific laptop models, please open an issue detailing your process.
This could help supporting many more potentially compatible laptops.

## Note
When in configuration:
- Rapid Charge Off
- Battery Conservation On

issuing the command `battmngr -sc 1` will turn on Rapid Charge mode but disable Battery Conservation mode.
It's possible to activate both Rapid Charge and Battery Conservation modes starting from configuration:

- Rapid Charge On
- Battery Conservation Off

and issuing the command `battmngr -sc 3`  
This configuration is not obtainable using official lenovo software and should be avoided.  
Check here for more: https://wiki.archlinux.org/title/Lenovo_IdeaPad_5_15are05#Note

## License

This project is licensed under the GPL-3.0 License.

