Inspired by this thread: https://forum.flipperzero.one/t/anyway-to-save-files-back-to-the-flipper-using-badusb/2372

Credit: Major credit to @LupusE for taking my original proof-of-concept, running with it, and making a proper example payload!

This proof of concept is for Windows-only.

BadUSB script that uses inline Powershell to enumerate which COM port the Flipper is connected to,
and then use Powershell's serial module to interface with Flipper's CLI and write text data to a specified file in Flipper's SD Card. It will automatically detect when the Flipper has exited BadUSB mode before writing the data to the SD card.

## Usage:
Attach Flipper to computer by USB cable and run the BadUSB script.  When the Flipper shows 100% completion, hit Back enough times to get to the Flipper application list (otherwise it won't save the data) and wait a moment and then remove the Flipper.

## Variables:
$d is the command who's output you want to exfiltrate to the Flipper's storage. Make sure to include |Out-String  as the last part of the command.

$BHID and $BPID allow you to specify the Device ID parameters of your Flipper.

$SPATH is the location on the SD card to store your exfiltrated data. By default, it saves to /ext/apps_data/exfil_data

## Example
This proof-of-concept stores the output of the Powershell Get-ComputerInfo

There are two payload examples included in the script. One will output to the Powershell console the state of the Flipper (BadUSB/NoFZ) to help you learn how to Back out of the BadUSB application and the timing.  The other payload is without debugging and without a delay if the Flipper is simply disconnected.
