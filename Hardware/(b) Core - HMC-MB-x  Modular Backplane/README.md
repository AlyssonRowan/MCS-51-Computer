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

