# Notes on Expo React Native

## Debugging builds for errors

- On the managed device, open the Settings app.
- Navigate to About `Phone -> Build Number`. Click on it 6 to 7 times, upon which You are now a developer is shown.
- Now, navigate back to `Settings -> Developer Options` and select the option `Enable USB debugging`.
- Connect the device to a computer through USB.
- On the computer, download the ADB Zip file from this link and unzip its contents.
- Once the contents in makedeviceowner.zip are extracted, open makedeviceowner folder.
- Now, open Command Prompt in the expanded folder and execute the command adb devices, which will show you the connected devices.
- Then execute `adb logcat > log_file.txt` command. This will generate the ADB logs and the logs will be saved to the log_file.txt file.
- If there are multiple devices showing, select the appropriate device with the `-s` option like so `adb -s <device_serial> logcat > log_file.txt`.
- Reproduce the issue on the Android device and press `Ctrl+C` on the Terminal Window to stop debugging.
- You can now share the log_file.txt file to MDM Support team.