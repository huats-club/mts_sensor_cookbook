# mts_sensor_cookbook

Dear learners, this repository contain the "recipes" to interface various common sensors found in MTS with the Raspberry Pi. Take some time to explore, experiment around, its ok to encounter certain challenges at the start.

## Raspberry Pi 4/5 GPIO Pinout

![Alt text](diagram/pi4_gpio.png)

## Regarding RPi.GPIO on Raspberry Pi 5
As of **2024-08-06**, **Raspbian Bookworm** includes a pre-installed `RPi.GPIO` which is not compatible with Raspberry Pi 5. To resolve this issue

```
sudo apt remove python3-rpi.gpio
pip3 install rpi-lgpio
```