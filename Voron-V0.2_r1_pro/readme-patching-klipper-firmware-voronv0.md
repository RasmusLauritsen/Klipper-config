# Flashing new Klipper version
Login to CM68 using SSH.

```bash
lsbusb      # Show USB IDs for the MCUs
cd ~/kiauh
./kiauh.sh  (Don't upgrade to alpha version)
```
In KIAUH select:
```
4) [Advanced]
4) [Build + Flash]
```
* Select correct settings for MCU in "make menuconfig"!
* See up-to-date in Github/wiki. 
* * [Catalyst](https://github.com/FYSETC/Catalyst_Kit_V2.0?tab=readme-ov-file), [M36_HUB](https://github.com/FYSETC/M36_HUB_V1/tree/main?tab=readme-ov-file), [Fysetc wiki](https://wiki.fysetc.com/docs/M36HUBV1).
* Select **Q** to quit and save config for a MCU.
```
1) Regular flashing method
1) make flash (default)
1) USB
Select CORRECT MCU!
Continue to flash
```

Repeat for the other MCU.