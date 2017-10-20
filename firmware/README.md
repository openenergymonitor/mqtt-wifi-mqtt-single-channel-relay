# Changelog

# v3190 Oct 20th 2017

- Compile with SDK: 2.1.0(7106d38) fix [KRACK WPA vulnerability](https://www.krackattacks.com/). See [forum post](https://community.openenergymonitor.org/t/wifi-relay-krack/5384/7?u=glyn.hudson)

# v2088 Mar 3rd 2016

- Inital stable release

***

## Update

- Via web interface

- Or via serial:

`esptool.py --port /dev/ttyUSB0 --baud 460800 write_flash --flash_freq 80m --flash_mode qio --flash_size 16m-c1 0x1000 XXXX.bin`