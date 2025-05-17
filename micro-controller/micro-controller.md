---
title: Micro-controller
description: Micro-controller basic
---

<br> [<kbd> <br> HOME <br> </kbd>][HOME] <br>

# Table of contents
- [Micro-processor & Micro-controller](#micro-processor--micro-controller)
- [GPIO](#gpio)
- [Interrupt](#interrupt)
- [ADC & DAC](#adc--dac)
- [PWM](#pwm)
- [Protocol & Interface](#protocol--interface)
- [Some Couple Term In Protocols](#some-couple-term-in-protocols)
- [USART](#usart)
- [I2C](#i2c)
- [SPI](#spi)
- [CAN](#can)
- [WiFi](#wifi)
- [Bluetooth](#bluetooth)
- [MQTT](#mqtt)

## Micro-processor & Micro-controller
**Micro-processor**: \
**Micro-controller**

## GPIO
**General-Purpose Input/Output Ports**  handles both incoming and outgoing digital signal \
They can be *INPUT* or *OUTPUT*, *LOW* or *HIGH* \
Also, they can be configurated for other functions, called *alternate function* \
`Pull-up resistor` is pulled *HIGH* the GPIO when the button is not pressed and pulled *LOW* the GPIO when the button is pressed \
`Pull-down resistor` is the opposite to *pull-up* \
`Open-drain` make the GPIO can only be *LOW* or *floating*, so we have to use external *pull-up* resistor.

## Interrupt

## Timers

## ADC & DAC
**Analog to Digital Converter** and **Digital to Analog Converter** are very important components in electronic equipments \
*ADC* and *DAC* architect won't be mention here, let's go to their parameters 
* Reference Voltage: 
* Resolution: 
* Quantization: 

## PWM
**Pulse Width Modulation**

## Protocol & Interface
A *protocol* usually come together with that *protocol's interface* so there are many people have ambiguous between *protocol* and *interface*. So, how are they different ? \
`protocol` is a set of rules for devices to communicate with others as *preamble*, *data length*, *conditions*, *crc*, ... and they need to be agreed by all devices \
`interface` is the way devices connect to others as wires, radio waves, ... 

## Some Couple Term In Protocols
**Synchronous** and **Asynchronous**: these are two important term in communication, they imply to *clock*. *Synchronous transmissions* are synchronized by a *clock* and *asynchronous transmissions* are not \
**Wire** and **Wireless**: just *wire* and *wireless* \
**Serial** and **Parallel**: data transmission *serial* or *parallel* (*e.g.* one wire or multi wires) \
**Simplex**, **Half-duplex** and **Full-duplex**: in simplex mode the signal is sent in one direction (only one device can sent data), in half-duplex the signal is sent in both directions but one at a time, in full-duplex signal is sent in both directions at the same time \
**Master** and **Slave**: *master* will be the *clock* controller \
**Server** and **Client**: *client* is requester and *server* serves

## USART
**Universal Synchronous/Asynchronous Receiver-Transmitter** protocol:
* Simplex, Half-duplex, Full-duplex
* Single Master - Single Slave (in UART there is not master and slave, both devices peer)

UART is asynchronous and USART is synchronous, their name said about it \
In UART there are some definitions that must be the same on devices:
* Baudrate: transceive data rate
* Start bit
* Stop bit
* Data frame length: it can be 5, 6, 7 or 8 (even 9 when don't use parity bit)
* Parity bit: used to check data correction. When parity bit = 0 number of bit 1 must be even and when parity bit = 1 number of bit 1 must be odd unless the data is wrong

I have never used USART so I don't have information about it exclude it is synchronous \
In addition, there is another mode called Multiprocessor UART, maybe I will add it later

## I2C
**Inter-Integrated Circuit**, also called **Two Wire Interface** protocol:
* Half-duplex
* Multi Master - Multi Slave
* Synchronous

## SPI
**Serial Peripheral Interface** protocol:
* Full-duplex
* Single Master - Multi Slave
* Synchronous

## CAN 
**Controller Area Network** protocol:


## WiFi


## Bluetooth


## MQTT


## DMA
*Direct Memory Access*

## Bootloader

[HOME]: ../README.md