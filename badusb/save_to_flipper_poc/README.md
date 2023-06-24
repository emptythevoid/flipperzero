Inspired by this thread: https://forum.flipperzero.one/t/anyway-to-save-files-back-to-the-flipper-using-badusb/2372/8

This proof of concept is for Windows-only.

BadUSB script that uses inline powershell to enumerate which COM port the Flipper is connected to,
and then use Powershell's serial module to interface with Flipper's CLI and write text data to a specified file in Flipper's SD Card.

Note: You have to get your timing correct.  When the Flipper is in BadUSB mode, the CLI is not available. 
Run the BadUSB script. As soon as it finishes, hit back twice. There is a configurable time delay (10 seconds)
to get the Flipper back to normal mode before the Powershell script tries to send the payload.

That's: BadUSB, Run, Wait for 100%, Back, Back
