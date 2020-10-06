# Changelog

# v3361 Oct 2019

- Support for using custom NTP server
- WPA Key extended to 64 characters
- [See forum thread](https://community.openenergymonitor.org/t/use-custom-ntp-server-on-the-wifi-relay/12097/21)
- Note: this version requires a "Full Flash" upload, see below

# v3190 Oct 2017

- Compile with SDK: 2.1.0(7106d38) fix [KRACK WPA vulnerability](https://www.krackattacks.com/). See [forum post](https://community.openenergymonitor.org/t/wifi-relay-krack/5384/7?u=glyn.hudson)

# v2088 Mar 2016

- Inital stable release

***

# Upgrade Firmware

- Via web interface

- Or via serial:

`esptool.py --port /dev/ttyUSB0 --baud 460800 write_flash --flash_freq 80m --flash_mode qio --flash_size 16m-c1 0x1000 XXXX.bin`

**To flash via serial USB:** Firstly disconnect the USB to power off. Then hold down the push button on the board and reconnect the USB, while still holding the button run the esptool commands shown on this page. Keep holding the button until esptool has completed flashing the firmware.

## Full Erase & Flash

```
esptool.py --port /dev/ttyUSB0 --baud 230400 write_flash --flash_freq 40m --flash_mode qio --flash_size 16m-c1 0x00000 blank.bin 0x01000 blank.bin 0x7C000 esp_init_data_default.bin 0x7D000 blank.bin 0x7E000 blank.bin 0x7F000 blank.bin 0x80000 blank.bin 0xFE000 blank.bin 0xFC000 blank.bin 0x100000 blank.bin 0x101000 blank.bin 0x1FC000 esp_init_data_default.bin 0x1FD000 blank.bin 0x1FE000 blank.bin 0x1FF000 blank.bin
```


Then upload the new firmware:

```
esptool.py --port /dev/ttyUSB0 --baud 230400 write_flash --flash_freq 40m --flash_mode qio --flash_size 16m-c1 0x000000 "boot_v1.7.bin" 0x001000 oem.v3361.bin
```
