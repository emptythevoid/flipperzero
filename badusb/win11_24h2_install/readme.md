Updated BadUSB scripts for installing Windows 11 24H2 from ISO

The installation scripts come in three parts that need to be run in order.

win11_24h2_part_1 clears out the primary disk 0.  It removes ALL DATA. This is required so that we don't have to fiddle with deleting each partition manually in part 2.

win11_24h2_part_2 performs the initial Windows 11 installation to disk 0.

win11_24h2_part_3 Creates a new local administrator account (that you need to set up into the script) and bypasses all the out-of-box experience crap.
