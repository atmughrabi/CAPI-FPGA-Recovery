
#  CAPI FPGA Recovery for Nallatech P385-A7

## Problem

You flash your FPGA card with a faulty image, and it stops showing up in you Power System.

## Dependencies

### FPGA
1. Nallatech P385-A7 card with the Altera Stratix-V-GX-A7 FPGA is supported.

### Tools
1. Starting from release 15.0 of Quartus II should be fine.
2. USB blaster, for flashing the FPGA Card.

## Steps

1. Open the Quartus GUI, then click on the "Hardware Setup" button on top left.  
2. Another box should pop up. 
3. Now click "Auto-Detect".  If you get an error saying that the JTAG scan was unsuccessful, then that could mean:
	* The connection between the USB/Ethernet Blaster and the adapter card is not on right.
	* PCI slot power to the adapter is off.
4. Otherwise, you'll see either that it found 2 devices or 3 devices in the scan.  
5. If there are only 2 devices, then it is unable to see the Flash due to the image that's already programmed on the card.  
	* So you will have to click on the FPGA (left-most chip) and "Change File" to "A7_a8sp.sof".  
	* Then click the "Program/Configure" box for the device and hit "Start".
6. After you do this, run "Auto-Detect" again and you should see 3 devices after the scan.  
7. You can now click on the "Flash" chip (upper right device) and "Change File" to the .pof that you want in the Flash.  
8. Click on "Program/Configure" box for the Flash device and "Start".

