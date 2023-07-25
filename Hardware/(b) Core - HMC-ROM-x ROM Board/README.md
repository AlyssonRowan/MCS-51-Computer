HMC-ROM-1 - 2764/27128 ROM Board v1.00
--------------------------------------

This is an interface designed to allow a pre-written EPROM
to be read by the processor. Both 2764 and 27127 EPROMs
may be used. The device only appears in the /PS address space

While the board may be configured by 8k blocks, while using
27128 EPROMs, the lower address should always be on a 16k 
boundary.

PROMs placed at the lower limit of the upper 32k of memory
(i.e. starting at 8000H) will allow the MCS-51 BASIC-52 
interpreter to access stored programs directly.

