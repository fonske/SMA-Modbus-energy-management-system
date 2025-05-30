# SMA-Modbus-energy-management-system
EMS in Home Assisant and node red

I made en Energy Management system in node red that runs as an adon in Home Assistant.

Goal: The goal of this EMS is to make my classic SMA inverter a bit smarter, so I can take advantage of some situations and but trying to avoid the negative situations using hourly dynamic elictricity prices. 

I started this in 2022, when my panels where installed. These are 12 panels (405W) South East and 10 panels (405W) South West.
The inverter is a SMA Tripower 8 SE with a SMA Home manager 2.

Important notice: I removed the SMA Home Manager 2 from Sunny Portal and only use Home assistant to control my system. The reason is that since the latest firmware update of the Home manager 2, modbus register 41255 that controls the curtailment, gets overwritten by the SMA Home manager 2.
SMA is working on their version of an EMS that will be released in Q3 of 2025, so they changed how the Home Manager 2 works with the inverter. 
You can only have control over the modbus register 41255 without the function of Home manager 2. 
I removed it from Sunnyportal and now my Home manager 2 works like a regular Energy meter. It still does basic control of my battery, but now I have full acces to all registers. 
If you have a classic SMA Enegery meter, then it should work without this caveat. 
