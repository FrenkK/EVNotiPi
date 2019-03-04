# EVNotiPi
Python Version of EVNotify

## Prerequisites
- Python 3
- Python Serial
- EVNotify API Python Library

## Installation
### Raspberry Pi
- `sudo apt-get update`
- `sudo apt-get upgrade`
- `sudo apt-get install bluetooth blueman bluez-tools python python-serial`
- `sudo bluetoothctl`
- (Plug OBD2 Dongle in car), eventually you also need to start the car
- `pairable on`
- `agent on`
- `scan on`
- Wait until you see a device called "OBDII"
- `scan off`
- `pair <MAC-of-Dongle>`
- PIN should be 1234
- `trust <MAC-of-Dongle>`
- `exit`
- `sudo crontab -e` (insert the following and save: `@reboot sleep 5 && rfcomm bind hci0 <MAC-of-Dongle> 1`
- `sudo reboot`
### EVNotiPi
- Copy `config.template.json` to `config.json`. Adjust the values for your needs
- Clone the EVNotify API Library (https://github.com/EVNotify/EVNotifyAPI).
- Create symbolic link from `EVNotifyAPI/libs/python/evnotify.py` to `evnotifyapi.py`
