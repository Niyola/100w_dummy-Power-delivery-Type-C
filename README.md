USB Type-C Power Delivery Tester

A USB-C Power Delivery tester and 100W dummy load, built as part of my Master's thesis at Brno University of Technology.

The board negotiates a USB-PD contract with any USB-C charger, power bank, or laptop, requests different voltages (5V, 9V, 12V, 15V, 20V), and measures what is actually being delivered in real time. It handles up to 100W.


What's inside

The STM32F072CB runs the USB-PD protocol stack. The FUSB302B from onsemi handles the CC line communication. The INA237 from Texas Instruments measures voltage and current on VBUS bidirectionally. It is a 4-layer board, roughly 100mm by 60mm, with dedicated inner planes for ground and 3.3V.


References I used

Twonkie v2.0 by dojoe — https://github.com/dojoe/Twonkie/tree/master
An open source USB-PD sniffer. I followed its approach for the FUSB302B wiring and the CC line level shifting.

TI TPS25751EVM — https://www.ti.com/tool/TPS25751EVM
Texas Instruments' official USB-PD evaluation board. I used it as a reference for the high-current VBUS layout and current sensing.


What I changed

I use a single INA237 for bidirectional current sensing instead of two separate chips. I added a screw terminal output so the board works as a dummy load tester, not just a sniffer. I redesigned the stackup as 4 layers with full ground and 3.3V planes for better power integrity at 100W. I also added test points for bring-up.

About me

Eniola Adesuyi, M.Sc. Communications and Networking, Brno University of Technology. Supervised by Ing. Ondřej Krajsa, Ph.D.
