Use this bin file to attempt to downgrade a compatible Logitech Unifying Receiver.  This is a dump of a known-vulnerable receiver running firmware 
RQR12.03_B0025. I have successfully flashed this to a receiver that was running a newer (patched) firmware.

Usage: 

If on Ubuntu, first do:

sudo apt install golang-go

Then:

git clone https://github.com/mame82/munifying

cd munifying

go build

sudo ./munifying flash -r /path/to/dump.bin

## Errors:
If munifying says "CAUTION: According to bootloader version, only signed firmwares are accepted! Closing Logitech Receiver in bootloader mode... Error provided firmware has no signature, but the bootloader requires one." This means that the firmware on the dongle has been updated to enforce signature checks, and cannot be downgraded to vulnerable firmware.
