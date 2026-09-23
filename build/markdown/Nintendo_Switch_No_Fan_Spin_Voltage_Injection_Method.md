---
title: "Nintendo Switch No Fan Spin Voltage Injection Method"
pageid: 880
revid: 2182
kind: explanatory_guide
source: "https://repair.wiki/w/Nintendo_Switch_No_Fan_Spin_Voltage_Injection_Method"
history: "https://repair.wiki/index.php?title=Nintendo_Switch_No_Fan_Spin_Voltage_Injection_Method&action=history"
permalink: "https://repair.wiki/index.php?oldid=2182"
last_edited: "2024-01-13T14:18:34Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Nintendo Switch"
infobox:
  Device: "Nintendo Switch"
  Type: "Method"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Nintendo Switch No Fan Spin Voltage Injection Method

Issues with the Nintendo Switch not firing up the fan when required are pretty common. A lot of the time it's an issue with the fan itself being faulty or it's an issue with a damaged joycon rail. The Nintendo Switch shares the same power rail for the fan as it does for the joycons. For whatever reason Nintendo decided it was a good idea to run both lines from the same mosfet, located just north of M92T36. Occasionally this mosfet fails 0L (open) and prevents power from passing through to the fan and joycon rails. This means we can't cool the system, and can't charge the joycons from the switch directly.

Fortunately, there's a neat little trick discovered by TheCod3r which allows us to fix this issue fast, and what's more, free! Using the voltage injection method fires the mosfet back into life and allows the circuit to work again. So far I've had 100% success rate using this method, with zero warranty returns when the mosfet was at fault. I've never had to actually replace the mosfet thus far.

Once you've removed the back cover and metal plate from the console, confirm the fan isn't firing up by playing the console for a little while. If the console overheats or the fan never kicks in, it has a problem. The first thing to do is to try and freely move the fan and spin it by hand. If the fan offers any resistance, doesn't spin at all or seems noisy (whining noise, bearing noises etc) try replacing the fan first. If that doesn't solve the problem, or if the fan feels fine then proceed with this guide.

Locate the VCC line on the fan. The image below will show you which pin you need to concentrate on. Once located, and with the console turned on inject 2.5-3.5v into the VCC line for 1-2 seconds. Continue tapping the pin with 2.5-3.5v a few more times. If the fan spins continuously stop immediately, the job is done! If the fan doesn't continue spinning you can test by connecting the joycons and see if they charge, or by using the console for a while and see if the fan starts to work. If it doesn't, you may be left with no other option but to replace the mosfet.
![Nintendo Switch Fan Pinout courtesy of [[GBATemp.net\]\]](images/1/13/450px-Nintendo_Switch_Fan_Pinout.jpg)

- Original article credit:* TheCod3r
