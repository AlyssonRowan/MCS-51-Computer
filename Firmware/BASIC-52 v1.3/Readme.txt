Version 1.3

Undoubtedly the best version of MCS BASIC-52 available is version 1.3. It was created by H.-J. Böhling and D. Wulf, and first published in Elektuur in February 2001 [6]. Apart from the article in Elektuur, the website of H.-J. Böhling is a great source of information on version 1.3. and many other useful enhancements and tools! The most important improvements and enhancements of version 1.3 are listed below:

All (well, almost all) known bugs from version 1.1 have been solved (Appendix B).

Like all MCS BASIC-52 versions that run in external EPROM memory, also version 1.3 is not capable of programming EPROMs. But an attractive alternative has been found. Instead of programming EPROMs, version 1.3 can program EEPROMs in exactly the same way as EPROMs in the original version. In address space 8000H-BFFFH a 16 kbyte area has been reserved for EEPROM memory. In Fig. 1 only the lower 8k of this area is used. The EEPROM can be used to store BASIC programs using the PROG commands (see chapter 3, p21 of the reference manual).

The new command ERASE has been added to erase the EEPROM. The erasing of the 16 kbyte EEPROM takes about 3 minutes.

The maximum value for XTAL can be set to 78MHz, so that the interpreter can even run on a 33MHz Dallas 80C320.

A new reset routine has been implemented so that version 1.3 recognizes many of the 8052 derivatives like: 80515, 80517(A), 80528, 80535, 80537, 80537, 80575 etc. Version 1.3 can detect if these processors have a separate baud-rate generator, and if so uses it.

The new “OPCODE” 43H reads a value from the result stack and assigns it to a BASIC variable (see chapter 9, p105 of the reference manual).

The authors were able to squeeze all this added functionality into 8 kbytes. To do this, the “ego-message” had to be sacrificed (see Fig. 8). 