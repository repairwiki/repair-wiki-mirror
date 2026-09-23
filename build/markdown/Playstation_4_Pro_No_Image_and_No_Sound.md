---
title: "Playstation 4 Pro No Image and No Sound"
pageid: 4640
revid: 7785
kind: repair_guide
source: "https://repair.wiki/w/Playstation_4_Pro_No_Image_and_No_Sound"
history: "https://repair.wiki/index.php?title=Playstation_4_Pro_No_Image_and_No_Sound&action=history"
permalink: "https://repair.wiki/index.php?oldid=7785"
last_edited: "2025-06-18T21:22:49Z"
contributors:
  - "Tiago199988"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Playstation 4 Pro"
  - "Stubs"
infobox:
  Device: "Playstation 4 Pro"
  Affects_parts: "Motherboard"
  Needs_equipment: "Soldering Iron, Hot Air Station, Microscope"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Playstation 4 Pro No Image and No Sound

## Problem description
The console does not display any Image or Sound when connected to a TV
![Example of Damaged HDMI Port on PS4](images/a/ab/Ps4_damaged_hdmi_port.jpg)

## Symptoms
- Console turns on but no image or sound is displayed on a TV

### Diagnostic Steps
The most common issues on a PS4 Pro that does not display any image is with the HDMI port or the HDMI encoder IC.

## **1.Examine the PS4 Pro HDMI port**
- Inspect the HDMI port for bent pins, debris, or physical damage.
- Inspect the connection of the HDMI port to the motherboard for any ripped pads or broken solder joints.
- If you have acess to the mozzwald HDMI adapter and a Mechanic Mechanic T-824 compare the readings of your port with a know good port.

![PS4 Pro HDMI Port Diode Mode Readings through Mechanic T-824 Tester](images/c/c0/PS4Pro-HDMI-Mechnic-Readings.jpg)

### 2. Examine the chokes between the HDMI encoder and the HDMI port.
- There are 4 chokes between the encoder and the HDMI port
- There are 8 data lines going through these chokes (each choke carries 2 data signals). The chokes must have continuity in parallel but not in cross.

![PS4 Pro HDMI Chokes](images/9/90/PS4_Pro_HDMI_Chokes.png)

## 3. Examine the PS4 Pro HDMI encoder circuit(MN864729)
- Check for any damage around the **MN864729** chip, like liquid damage or physical damage (cracks,holes).
- Check for any shorts on the surrounding components.
- Check for missing voltages the HDMI circuit a good working hdmi circuit must have these voltages with the console ON

![PS4 Pro encoder Voltages](images/4/4a/PS4_Pro_encoder_Voltages.png)

## Repair Steps
### **Replace the HDMI port**
The easiest way to replace the HDMI port is to use the "hot swap" method it consists of heating the port from below and when the solder is liquid you lift the old port and install the new one while the solder is still liquid, there are a few videos on youtube how to this heres an example.

Video by TheCod3r [https://www.youtube.com/watch?v=pcdsfq9DPl8]

After soldering the new port make sure every pin as a good connection to the pad on the motherboard.

Make sure the solder flooded well on the anchor points both on the top side of the board and the bottom.

The PS4 Slim and Pro use the HDMI port.

## Replacing the HDMI Chokes
Use a hot air rework station to heat the solder joints of the old choke. Apply heat evenly until the solder melts, then gently remove the choke with tweezers.

After removing the choke, clean the pads of old solder using a soldering iron and solder wick.

Apply a small amount of solder to the cleaned motherboard pads.

Align the new choke and apply heat (use a low air speed to avoid dislodging the choke). When the solder beneath the choke melts, surface tension will pull the component into place.

Both the PS4 Slim and Pro use the same chokes on the HDMI circuit.

### Replacing the HDMI encoder (MN864729)
  - Desoldering the Old Chip:**

- Set up a board preheater (if available) to warm the motherboard, as it requires significant heat.
- Apply heat to the MN864729 chip from above using a hot air station or soldering iron. Heat for several seconds until the factory solder begins to melt.
- Gently nudge the chip with tweezers. If it moves, it’s ready to be lifted off.
- While the board is still hot, use solder wick and a soldering iron to clean old solder from the motherboard pads.

  - Preparing the Motherboard and New Chip:**

- Apply a thin layer of new solder to the cleaned motherboard pads. Avoid excess solder, especially in the center square.
- Pre-tin the pads of the new MN864729 chip with a small amount of solder to ensure good contact.

  - Soldering the New Chip:**

- Align the new chip on the motherboard. Match the dot on the chip to the small triangle marker on the motherboard for correct orientation.
- Heat the chip from above using a hot air station. Watch for the solder to melt, indicated by slight chip movement.
- Gently touch the chip with tweezers to let surface tension settle it into place. Avoid excessive force.

  - Inspection and Cleanup:**

- Inspect all connections under a microscope . Ensure there are no solder bridges between pins.
- If any connections look faulty, gently touch the affected pad with a soldering iron to reflow and correct.

Both the PS4 Slim and Pro use the same HDMI encoder.

### Final Testing
  - Basic Display and Sound Test:**

- Connect the console to a TV or monitor using a high-quality HDMI cable.
- Power on the console and verify that both image and sound are output correctly.
- Check for clear visuals without artifacts, flickering, or distortion, and confirm audio is transmitted without issues.

  - Auto-Detect Resolution Function:**

- Ensure the console automatically detects and sets the appropriate resolution for the connected display.
- Test switching between different resolution settings (e.g., 1080p, 4K) to confirm the HDMI encoder handles them correctly.

  - 4K Display Test:**

- Connect the PS4 Pro to a 4K-capable TV or monitor that supports 4K resolution at 60Hz
- Launch a 4K-compatible game or app to verify the console outputs a stable 4K image with no stuttering, black screens, or signal loss.
