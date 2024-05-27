## How to Flash StrideMax Dual FD V2 - USB
1. Enter to your raspberry via SSH trough MobaXTerm
2. To compile the micro-controller code, start by running these commands on the Raspberry Pi: 
cd ~/klipper/
make menuconfig
3. Then select Raspberry Pi RP2040
4. Run Make
5. This will output a file into klipper/out called “klipper.uf2”
6. Next step is to plug in the StrideMax board into the computer by holding the BOOTSEL button. This will open a 
new window in your computer like an external drive, but this is the RP2040.
7. Delete what’s inside and copy the file “klipper.uf2” to it. The windows will automatically close. This means that 
our board is flashed.
8. Back in console and with the board connected through USB, we will make a search of our devices with this 
command:
ls /dev/serial/by-id/*
Which will return the MCU address
(In this case there are two boards connected at the same time)
9. Add it to your printer.cfg
##StrideMax Dual
[mcu stridemax_dual_X]
serial: /dev/serial/by-id/usb-Klipper_rp2040_E6612C771F892629-if00 – REPLACE WITH YOUR SERIAL –
10. Copy the config from GitHub according to your needs 
https://github.com/FYSETC/Stridemax_Dual_FD/tree/main/klipper
