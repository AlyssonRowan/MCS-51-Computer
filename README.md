# MCS-51-Modular-Computer


MCS-51 based highly modular computer system
-------------------------------------------

This project aims to bring forward an MCS-51 based 
computer system centered around a series of relatively
simple modules sharing a modular bus backplane.

The overall design uses a number of boards designed within 
the limitations of low-cost PCB prototyping houses and free
PCB design software, i.e.
- Two signal planes (front and back)
- A maximum board size of 100mm x 100mm
  (yes, I know that some of them limit you to 100 x 80mm)
- A maximum of 300 connections per PCB
- A maximum of 2 signal (or groundplane) layers

Three card sizes have been defined and templates generated
based on the 1U Eurocard - 
- Full 1U Eurocard (100mm x 160mm)
- Half 1U Eurocard (100mm x 80mm)
- Short 1U Eurocard (100mm x 100mm)

These templates include placement masks for the bus connectors

NOTE:
----
Some of the simpler boards exist only as PCB files,
in these cases, component values are marked on-board
instead of component references.

The affected boards are:
- Modular Backplane (2 boards)
- 4-slot Production Backplane
- Integrated Backplane (MOBO and daughterboard)
- Bus Daisy-Chain board


Central Processor Board
-----------------------
- HMC-PR-1 AT89s51 Processor Board

The processor chosen for this project is the Atmel
AT89S51 and AT89S52 microcontroller. These have
4k and 8k of ISP Flash Memory respectively.

The processor board is set up without user SRAM and 
is ready to accept firmware as a basic development 
board. The serial lines are buffered and brought out 
to a header (TTL signals) for connection to a user 
console. RS232 is available via the Front Panel board.

Console (serial) signals are also carried on the bus
ready for embedded terminal hardware.


Main Memory Boards
------------------
- HMC-MMB-1   HY6264A (8k x 8bit SRAM) x 4
- HMC-MMB-2 - Configurable W24257AJ (32k x 8bit SRAM)

Two versions have so far been designed 
- one accepts a 32k x 8 fast SRAM chip, and is 
configurable in 8kB blocks.
- the second accepts up to 4 8k x 8 fast SRAM chips

Both versions may be located in upper OR lower memory space.
Up to two of these boards may be installed.


Program ROM Boards (Under development)
------------------
Ultimately, these boards will accept

- UV-EPROM
- EEPROM
- FLASH PROM

And will provide storage for compiled programs
(upper PStore) and System programs (lower PStore)


Modular Computer Bus
--------------------
The decision was made to use low-cost, highly available
standard 0.1" double row headers in order to reduce the 
board pin count while providing just a few spare lines 
above the bus minimum requirement. These are the same 
connectors formerly used for PC floppy and hard disk 
drives.

Although polarity is respected, just in case ribbon cable
is used, it is actually maintained by the polarisation 
forced by the dissimilar connectors on the backplane.


Modular Backplane
-----------------
- HMC-MB-1 (Slot A)
- HMC-MB-2 (Slot B)

The backplane comprises two boards, one carrying the 
40-way bus that includes the default signals from the 
MCS-51 MPU and the other, a 24-way bus with additional 
signals and 5V power. This second board also includes
decoupling capacitors per backplane slot.

The two boards are designed to sit side by side, and are
able to be stacked, extending the basic backplane from 
the basic five slots to (theoretically) any number of 
slots. It is not recommended that more than two modules
be daisy-chained without bus terminations.

A separate, hard wired 5.0V 2A (or more) power supply is
required to power the bus.

M2 mounting holes are provided for attachment of lateral 
support bars (Grounded, recommend: 6mm square Aluminium,
use M2 stainless washers to stand off from PCB) and cage 
sides (Isolated, recommend: 4mm acrylic). Half-holes are 
provided on the junction between the two boards in order
to facilitate a third point of attachment to the support 
bars.


Integrated Backplane
--------------------
- HMC-IB-1 (MOBO)
- HMC-IB-2 (Bus)

This is a pair of boards that are stacked using extended 
pin header sockets. 

The motherboard is a single 100mm square board which
includes basic front panel functionality and power feed
to the bus. A separate, hard wired power supply (5.0V 2A) 
is required.

The daughterboard provides a 4-slot bus powered via the 
motherboard.

It is recommended that this item not be daisy-chained
without very careful consideration. The board is fused
at 2A.

There is no RS232 console option on this PCB. This needs
to be provided separately if required. 

A low frequency clock "pulse" generator is provided for 
applications that require a low-frequency, semi-stable 
clock pulse for operation in the development stage.

The daughter board, built with standard sockets (i.e.
not wire-wrap form) may be used independent of the parent
board as a simple, no-frills 4-slot backplane. A mountable
version of this PCB is available.

With only a plug and a socket, the daughter board could 
also be used as a slot extender for service use.


4-Slot Production Backplane
---------------------------
- HMC-PB-1

This is functionally identical to the 4-slot daughterboard
for the integrated backplane kit, though with the addition
of mounting holes.


Daisy Chain Boards
------------------
- HMC-DCB-1 Short link for Modular Backplane use
- HMC-DCB-2 Long link for integrated backplane use

These board are supplied as two separate PCBs.

One narrow PCB for interlinking two Modular Backplane
segments while maintaining system board separation.
The wider is for linking an integrated backplane with 
a modular backplane segment.

Linking an integrated backplane with a modular backplane
is not recommended other than for development purposes.


Active Bus Terminator
---------------------
- HMC-ABT-1
While not strictly necessary, this short board is designed
to be inserted in the first and last physical slots on the 
bus, and should reduce signal reflections and timing issues
on the bus - especially when a longer bus is used.
