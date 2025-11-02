### communication protocols

#### I2C

**I2C (Inter-Integrated Circuit)** is a synchronous, multi-master, multi-slave serial communication protocol that operates using only two lines: serial data (SDA) and serial clock (SCL). The master device generates the clock and initiates communication, while each slave is identified by a unique address. Data transfer occurs in packets with addressing and acknowledgment mechanisms, supporting multiple devices with minimal wiring—making I2C very popular for connecting various sensors, memory chips, and peripherals to microcontrollers in embedded systems.​

#### USART

**USART (commonly used as UART—Universal Asynchronous Receiver/Transmitter)** is an asynchronous, point-to-point serial communication protocol that uses two lines: transmit (Tx) and receive (Rx). Unlike I2C, UART communication does not require a shared clock; instead, both devices agree on a fixed baud rate. Data transmission involves encapsulating payloads with start and stop bits for synchronization. UART is favored for simple, direct data exchange between two devices, such as microcontroller debugging, GPS modules, or serial communication with computers.​

### web serial API

The Web Serial API provides a mechanism for websites to interact with serial devices connected to a user's computer, such as microcontrollers, 3D printers, and other serial-based hardware. This API bridges the gap between web applications and the physical world by enabling communication over a serial port.

### hardware abstraction layer (HAL)

A [Hardware Abstraction Layer](https://www.google.com/search?q=Hardware+Abstraction+Layer&sca_esv=0b1bbd70689b2a31&sxsrf=AE3TifNOeVWMqJsDATA53fIQHdYbp9ZZqA%3A1761801118563&ei=nvMCafmMIpL2seMPn6jvwQo&oq=hardware+ab&gs_lp=Egxnd3Mtd2l6LXNlcnAiC2hhcmR3YXJlIGFiKgIIADIFEAAYgAQyChAAGIAEGBQYhwIyBRAAGIAEMgUQABiABDIFEAAYgAQyCxAuGIAEGMcBGK8BMgUQABiABDIFEAAYgAQyBRAAGIAEMgUQABiABEiMGFDrBljBEnADeAGQAQCYAYYBoAHACaoBAzQuN7gBA8gBAPgBAZgCDqAC8AnCAgoQABiwAxjWBBhHwgIKECMYgAQYJxiKBcICBBAjGCfCAgsQABiABBiRAhiKBcICEBAAGIAEGLEDGEMYgwEYigXCAgoQABiABBhDGIoFwgILEAAYgAQYsQMYgwHCAhEQLhiABBixAxjRAxiDARjHAcICEBAjGPAFGIAEGCcYyQIYigXCAhYQLhiABBixAxjRAxhDGIMBGMcBGIoFwgIQEC4YgAQY0QMYQxjHARiKBcICDRAAGIAEGLEDGEMYigXCAggQLhiABBixA8ICCxAuGIAEGLEDGNQCwgINEAAYgAQYsQMYFBiHAsICCBAAGIAEGMkDwgILEAAYgAQYkgMYigXCAggQABiABBixA8ICDRAAGIAEGEMYyQMYigWYAwCIBgGQBgiSBwM1LjmgB7hksgcDMi45uAfnCcIHBjAuMTAuNMgHIw&sclient=gws-wiz-serp&ved=2ahUKEwjU2rTTlMuQAxUvRmwGHbz7KFQQgK4QegYIAAgAEAU) (HAL) is ==a software layer that acts as an interface between a computer's hardware and its operating system or other software==. It hides the low-level, device-specific details of the hardware from the rest of the software, allowing developers to write programs that are portable across different hardware configurations. A HAL provides a standardized set of functions and protocols, simplifying communication and saving development time.
