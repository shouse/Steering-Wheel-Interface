# Steering Wheel Interface

Android application for interfacing with the steering wheel radio control buttons in certain Jeep/Chrysler/Dodge vehicles.

## Purpose

This project exists primarily as an example of how to interface an Android device with a vehicle bus using an inexpensive ELM327 based OBDII scan tool.

This is NOT an OBDII or "code reader" type application! A scan tool is used only to provide the interface to other vehicle buses that happen to also use OBDII standard protocols (SAE J1850 PWM, SAE J1850 VPW, ISO 9141-2, ISO 14230-4 KWP, ISO 15765-4 CAN, SAE J1939 CAN).

The application is not likely useful to many people exactly as-is, but is designed to be extended to work with your specific vehicle/scenario. Note that only USB scan tools are currently supported, though adding support for BlueTooth  should be relatively simple.

## Getting Started

### To test the application as-is requires:

+	An Android device with USB Host support running Android 4.1 (Jelly Bean) or newer.
	
	Note: The majority of the functionality only requires Android 3.1 (Honeycomb). If you remove or refactor the "settings screen" functionality, you should be able to compile and deploy to Honeycomb devices.
	
	Root access is required for some functionality.

+	An ELM 327 based USB scan tool
	
	Note: Many of the cheap eBay clones do not implement every protocol correctly and therefore may not work. This one is known to work: [http://www.amazon.com/ScanTool-423001-ElmScan-Diagnostic-Software/dp/B002PYBZJO/](http://www.amazon.com/ScanTool-423001-ElmScan-Diagnostic-Software/dp/B002PYBZJO/)

+	A USB OTG cable	(or an Android device with a native USB Host port)

+	A Jeep/Chrysler/Dodge vehicle with a SAE J1850 VPW base PCI Bus (many late 90's through mid 2000's models)

Compile and deploy the application. Plug the scan tool into the vehicle via the OBDII diagnostic port and into the Android device through the USB OTG cable. 

Respond to the Android prompt regarding USB device being attached by selecting this app to launch. It is recommended you select the "always" option. (Note: if you already have a default application for USB-Serial devices, you will need to clear that setting.)

A notification should be seen saying the Steering Wheel Interface started. Click the notification for the settings screen where you can adjust the baud rate for your particular scan tool. You will need to restart the app for the new baud rate to take effect.

Press your steering wheel radio control buttons. By default, play/pause, next/prev track, volume up/down, and go-to-home-screen actions are supported. Only the volume actions do not require root, the other actions will fail silently on non-rooted devices.

Tested and confirmed working on a Motorola XOOM 4G running the CyanogenMod 10 ROM with a 2003 Jeep Grand Cherokee.

### Using with other vehicle makes:

(documentation pending)

## Copyright and License

Copyright 2013 Kristoffer Smith and other contributors

Except for external references, this project is licensed under the MIT License.

[http://opensource.org/licenses/MIT](http://opensource.org/licenses/MIT)

## Contributing

Pull requests are welcome! Please contact me if you'd like to do a major re-work or extension of the project.

[https://github.com/theksmith/Steering-Wheel-Interface](https://github.com/theksmith/Steering-Wheel-Interface)

## Credits

### Authors

+	Kristoffer Smith ([http://theksmith.com/](http://theksmith.com/))

### Contributors

+	none yet

### References & Dependencies

+	This project uses the usb-serial-for-android library. Source code is currently included instead of the binary as minor changes were required. [http://code.google.com/p/usb-serial-for-android](http://code.google.com/p/usb-serial-for-android)