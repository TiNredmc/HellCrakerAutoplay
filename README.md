# Work in Progress
# HellCrakerAutoplay (Specific for Sin machine)
HellCracker is the hardware-based autoplayer. By using the LDR and Schmitt trigger. We can use Interrupt timer to calculate how the fast and slow step should be. By using my Teensy 2.0++ (clone) to emulate HID keyboard for W A S and D button pressing. 

# How timing works ?
In Sin machine phases. There are the metal chains on the left and right of screen. And the moving speed is equal (moving along with the bridge) to the bridge in the middle of screen (This is where the player need to avoid the White chain). The Sin machine chain on either left or right side are having the see-through hole that we can see the orange (bright) background. Luckily that the brightness of the Metal chain (dark) and the backdround is entire different. So I can use LDR and schmitt trigger to output the period of swithing between Dark and Bright. 

After we got that data. LDR connected to other resistor forms the voltage divider. By using Schmitt trigger. We can use certain voltage level to represent logic 1 or logic 0, Like we can set 1V as output logic low and 3 volt as logic high. Basically we remap the analog voltage to digital logics. 

After we got the stable digital logic. We can use the logic analyzer to see the waveform period (I have arduino uno, That's my only logic analyzer (sump logic analyzer)). Then later use that imformation to calculate when to <emulate> the button.
  
HID emulation and interrupt timer is done by My Teensy 2.0++ (clone). using Teensyduino will be great. I already decoded the player movement steps of phase 1. Then later turn it into some form of array for keypress emulator (HID class).
