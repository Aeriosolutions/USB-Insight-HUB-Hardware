# USB Insight HUB Hardware

>[!Note]
>Production hardware version is C0.

>[!Note]
>The firmware and software is published in the [USB-Insight-HUB-Software](https://github.com/Aeriosolutions/USB-Insight-HUB-Software) repository.

## Block Diagram
![Block Diagram](https://github.com/Aeriosolutions/USB-Insight-HUB-Hardware/blob/main/Images/Block%20Diagram%20B0%20landscape.svg)
## Main components
1.	A base PCB board with the functions of: Upstream data/power usb port, USB Hub Subsystem, Power meter and control, USB signal flow control, Downstream USB Ports, Power Port and Power Controller. In addition, contains an auxiliary microcontroller serving as IO extender.
2.	An interface PCB board with the main microprocessor, 3 displays, buttons and additional interface ports.
3.	A board to board flat cable.
4.	Mechanical components: standoffs, screws, transparent acrylic faceplate and protective acrylic covers and plates. This last one can be interchanged with a plastic (ABS) case if more protection is required for the boards.
![Exploded View](https://github.com/Aeriosolutions/USB-Insight-HUB-Hardware/blob/main/Images/Exploded%20view%20C%20s.jpg)

## Features & Specifications
### USB Interface

- USB 3.0 hub functionality is provided by the Renesas uPD720210, which supports USB 2.0 lines (Low, Full, and Hi-Speed) as well as USB 3.0 lines (5 Gbps Super-Speed). All USB communication is carried out as a regular USB Hub; transactions are not intercepted or monitored in any way.
- One upstream USB 3.0 Type-C port for data and power (up to 3 A @ 5.5 V)
- Three downstream USB 3.0 Type-A ports
- Individual USB 2.0 D+/D- switches for each downstream port
### User Interface
- 3x color 1.3-inch TFT displays (240x240), IPS, 170° viewing angle, 250 NITs
- 3x mechanical push buttons for power and data control and 1x setup button
- A dedicated latching switch to control device-wide power
- Remote Web UI provided via Wi-Fi (AP or client).
### Controllers
- An Espressif ESP32-S3 microcontroller running Arduino code provides display, metering, control, and communication with the host computer (via USB 2.0).
- STM8S003K3 is used as an IO extender.
- Programming headers for the primary and all auxiliary microcontrollers
### Power
- One dedicated USB Type-C connector for auxiliary power up to 5 A @ 5.5 V.
- A dedicated power and energy monitor (PAC1943) for current and voltage monitoring on each downstream port, with resolutions of 1 mA and 1 mV.
- Individual switch (AP22653) for power control to each downstream port with hardware current protection configurable to 0.5, 1.0, 1.5, and 2.0 A. Reaction time is under 6 ms.
- Software overcurrent protection configurable in 1 mA steps. Reaction time is under 20 ms.
- Software Reverse current protection configurable in 1mA steps. Reaction time is under 20 ms.
- All data and power inputs and outputs are properly protected against ESD.
### Host-Computer Compatibility
- Readily available Windows, Linux, and MacOS drivers for the USB Hub chip and the ESP32-S3 microprocessor.
- USB property-extraction software for Windows
- Work-in-progress USB property-extraction software for Linux and MacOS
### Other Features
- Downstream ports are spaced further apart than they are on most hubs
- Acrylic protection for the PCBs and displays
- Additional STEMMA QT connector to extend functionality
- 2.4GHz Wi-Fi wireless interface
