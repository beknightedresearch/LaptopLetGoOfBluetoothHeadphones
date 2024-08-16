# LaptopLetGoOfBluetoothHeadphones
Scripts and Windows Tasks to help force a Windows Laptop to disconnect from Bluetooth headphones when the laptop is closed. Otherwise, it can be difficult to connect the headphones to another device.

The .ps1 files are Powershell scripts. 

They depend upon the Bluetooth Command Line tools: https://bluetoothinstaller.com/bluetooth-command-line-tools.

Further, the script bluetoothSwitch.ps1 originated at: https://superuser.com/questions/1168551/turn-on-off-bluetooth-radio-adapter-from-cmd-powershell-in-windows-10 (with a https://creativecommons.org/licenses/by-sa/4.0/  license)

To use:
1. Install Bluetooth Command Line tools.
2. Download files, place the *.ps1 files somewhere permanent
3. Edit disconnectSonyHeadphones such that
   a) The path to Bluetooth Command line tools is accurate
   b) The xx:xx:xx:xx is replaced with ID for the headphones (can be found with btdiscovery or in Devices & Printers)
4. Edit restartBluetooth such that the path to bluetoothSwitch is correct
5. Update the file paths in the *.xml files
6. Go to Task Scheduler and import the *.xml files as tasks. Ensure the user to run under is correct.


Known limitations:
The disconnect task does not always run immediately after closing the lid, probably due to modern standby.
If the headphones are power-cycled, however, the task usually runs at that point, allowing the headphones to be connected to another device.

The restartBluetooth script cycles the Bluetooth to off and then back on when a user logs in. Without it, the headphones disconnected can not be reconnected to the laptop. Currently, the Bluetooth is always on after a user logs in.
