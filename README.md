# Enderwire Docs

**NOTE!!! THIS DOCUMENT IS INCOMPLETE AND A WORK IN PROGRESS!!! MANY ITEMS MAY CHANGE OR BE REMOVED/REWORDED!!!**


This repository outlines the steps to convert your Ender 3 into a CoreXZ movement printer based on the Voron Switchwire. There wasn't really a lot of consolidated information about this so I decided to write it up into a guide.

**Disclaimer**: Proceed with caution, many steps in a conversion could lead to injury especially when dealing with mains wiring. Do so at your own risk, I take no responsibility or liability for your own actions, this guide is informational only.

Voron Discord: https://discord.com/invite/voron

Select a Country in the Rules channel to be able to see the #ender_conversion_chat thread https://discord.com/channels/460117602945990666/658599170734686219

# Prerequisites:
* Your printer is an Ender 3 with either a 2040 or a 4040 Y-axis extrusion.
* Your printer has a 32-bit mainboard (Creality 4.2.2 or 4.2.7) if you plan to reuse the Creality mainboard.
* You have access to a printer that can print ABS parts (the stock Ender 3 with the white PTFE tube and non-all metal hotend is not recommended or even really safe to print ABS with)
* You are familiar or comfortable enough building a 3D printer from scratch, and are able to figure out how to source your own parts and read documentation.

# Models and Repositories
### Ender Printable Conversion Parts:
*For Enders with a 4040 y-extrusion:*
**DarkDog's Rev.2 Conversion:** https://github.com/boubounokefalos/Ender_SW/tree/Rev.2

*For Enders with a 2020 y-extrusion:*
**Gizzle's Non-Pro Conversion:** https://github.com/VoronDesign/VoronUsers/tree/master/printer_mods/Gizzle/ender-3_(pro)_switchwire
**Thomasjfen's Non-Pro Conversion:** https://github.com/thomasfjen/enderwire_nonpro

If you have a non-pro Ender 3 (aka: the 2040 y-extrusion version) it's recommended to print the majority of DarkDog's parts, and use the y-axis parts from Gizzle or Thomasjfens repositories. (You'll have to mix and match and figure out what will work since the non-pro is not really a mainstream conversion)

### Stealthburner Repository:
The Enderwire conversion you can really use whatever hotend and toolhead you can find parts for (again, you'll have to do the legwork to find models and info about these not-commonly-used setups) -- however for the easiest time it's recommended to use the Stealthburner toolhead.

The repository for the Stealthburner toolhead can be found here: https://github.com/VoronDesign/Voron-Stealthburner/tree/main/STLs

# Parts:
### Bill of Materials (BOM)
These are the parts that you will need to source (aka: buy) to make the conversion happen. 

**Note: You also need to source all the parts listed in the Stealthburner BOM!** Found here: https://vorondesign.com/voron_stealthburner

**Notes:** Fasteners quantities include an additional 10% over what is required just in case. As for the Linear Rails, you only need 4 if you are doing a non-pro conversion). For the Drag Chain, usually ONE chain will do, but you'll need to buy 2 additional *sets* of ends for it then.

**Printed**
|Part|Quantity|
|----------|----------|
|Gantry, Electronics|All|
|Aesthetic (Grills, Extensions, Panel Mounting, Misc)|All|
|Toolhead (Stealthburner)|All|

**Electrical**
|Part|Quantity|
|----------|----------|
|16awg Wire (mains to PSU)|1 set|
|20awg FEP/PTFE Wire (MCU to Toolhead Heater)|1 set|
|24awg FEP/PTFE Wire (MCU to Toolhead)|1 set|
|??awg FEP/PTFE Wire (Heatbed to MCU)|1 set|
|24awg Silicone Wire (5v PSU to Pi)|1 set|
|Mean Well RS-25-5 PSU (For RPi)|1|
|Mean Well LRS-350-24 (Optional, recommended)|1|
|Axial Fan 6040 or 6020 24v (chassis fan)|1|
|Raspberry Pi 3b+ or better|1|
|Bigtreetech SKR Mini E3 v3 (Optional, recommended)|1|
|Omron TL-Q5MC2 - NPN Inductive Probe|1|
|SPDT KW10 Limit Micro Switch|2|
|BAT85 Diode|1|
|NEMA17 Stepper Motor 17HS15-1504S1 (Optional, recommended)|3|
|Mini 12864 Display (Optional)|1|
|LED Strip 240mm 24v (Optional)|2|
|Inlet Power Socket IEC320 C14 (Optional, recommended)|1|


**Fasteners + Hardware**
|Part|Quantity|
|----------|----------|
|Fasteners + Hardware|m3x5x4 Heat Set Inserts|70|
|Fasteners + Hardware|2020 m3 Roll-in T-nuts|30|
|Fasteners + Hardware|2020 m5 Roll-in T-nuts|75|
|Fasteners + Hardware|m3 x XX Socket Head Cap Screws|x|
|Fasteners + Hardware|xxx|x|
|Fasteners + Hardware|xxx|x|
|Fasteners + Hardware|m5 x XX Socket Head Cap Screws|x|
|Fasteners + Hardware|xxx|x|
|Fasteners + Hardware|xxx|x|
|Fasteners + Hardware|m3 x XX Button Head Cap Screws|x|
|Fasteners + Hardware|xxx|x|
|Fasteners + Hardware|xxx|x|
|Fasteners + Hardware|m5 x XX Button Head Cap Screws|x|
|Fasteners + Hardware|xxx|x|
|Fasteners + Hardware|xxx|x|
|Fasteners + Hardware|m3 x XX Flat Head Cap Screws|x|
|Fasteners + Hardware|mX x XX Self Tapping Screws|x|

**Motion**
|Part|Quantity|
|----------|----------|
|Motion|Linear Rail 12H 300mm, Stainless Steel LDO-SLR12H-300|5|
|Motion|F695-2RS Bearings|20|
|Motion|Key-bak **Super48** - 13oz - 36"|1|
|Motion|Pulley, 2GT, 20T, (5mm ID 6mm W)|3|
|Motion|Gates Open Belt, 2GT, 6mm|4 meters|
|Motion|Drag Chain, 10x10mm, R18, 15 links|1|
|Motion|Drag Chain, 10x10mm, R18, 18 links|1|
|Motion|Drag Chain, 10x10mm, R18, 26 links|1|

**Toolhead**
|Part|Quantity|
|----------|----------|
|Toolhead|PTFE Teflon Tube (4mm OD 2mm ID) - 10cm|1|
|Toolhead|PTFE Teflon Tube (4mm OD 3mm ID) - 1.2m|1|

**Enclosure and Deck**
|Part|Quantity|
|----------|----------|
|Enclosure and Deck|6x3mm Neodymium Magnets|10|
|Enclosure and Deck|3M VHB Tape (3/4")|1 roll|
|Enclosure and Deck|Acrylic Panel(s)|???|
|Enclosure and Deck|ACM or ABS Panels|???|

### Reuseable Parts
These are the parts that you will reuse from your existing Ender 3 (assuming it is a stock Ender 3, if you replaced stuff, your mileage may vary)

* **Frame** - all parts of your Ender 3 frame will be used for the conversion
* **Mainboard** (MCU) - if you have the v4.2.2 or v4.2.7 32-bit Creality mainboard, that will be enough for the conversion
* **Power Supply** - the stock 350w 24v 15a power supply will be good enough
* **Stepper Motors** - you will only need the X, Y, and Z motors. The extruder motor is not used (see Stealthburner section)
* **Power Inlet** - this is the part where you plug the power cord into the Ender. It will be needed to complete the conversion.
* **Hotend** - Sort of. You *can* get away with this hotend, but it's recommended to get an e3d v6 or better hotend. 
* **Heatbed and Heatbed Y-Carriage** - The heatbed is actually pretty good, but you will have to drill out your y-carriage (more on that later)

