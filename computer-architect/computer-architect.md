---
title: Computer Architect
description: Computer architect basic
---

<br> [<kbd> <br> HOME <br> </kbd>][HOME] <br>

# Table of contents
- [Table of contents](#table-of-contents)
- [1. Von Neumann & Harvard](#1-von-neumann--harvard)
- [2. Little endian & Big endian](#2-little-endian--big-endian)
- [3. Memory Architect](#3-memory-architect)

## 1. Von Neumann & Harvard
**Von Neumann** is the computer architect that have intercommunity bus for program memory and data memory \
**Harvard** is the opposite, so it have better performance

## 2. Little endian & Big endian
**endian** is a storage mechanism so it is opposite to our thinking \
**Little endian** is from LSB to MSB and **Big endian** is the opposite

## 3. Memory Architect
There are two memory types in computer: **volatile** and **non-volatile** \
`volatile` with  representation is `RAM`, also called memory, loses contents when power is off, a temporary workspace for data because it is high-speed \
Some *volatile memory*:
* SRAM or *static RAM*: fast, small capacity, high energy consumption, used for *caches*
* DRAM or *dynamic RAM*: slower than SRAM, higher capacity, requires periodic refresh, used for *main memory*

`non-volatile` with  representation is `ROM`, also called storage, preserves contents when power is off, used to store data \
Some *non-volatile memory* (their name say all about them):
* PROM or *programmable ROM* and MROM or *mask ROM*
* EPROM or *erasable programmable ROM*
* EEPROM or *electrically erasable programmable ROM*

There are also some additional memory types:
* Cache: *SRAM* application
* Flash: erased a "block" at a time, limited number of program/erase cycles 
* Bootloader: on power up, transfers data from non-volatile to volatile memory
* Disk

Memory component speed ordered from fastest to slowest: register, cache, main memory, non-volatile memory, hard-disk drives, optical disk, magnetic tapes

<br> [<kbd> <br> FEEDBACK <br> </kbd>][FEEDBACK]<br>

[HOME]: ../README.md
[FEEDBACK]: https://github.com/friendlydenji/notebook/discussions