---
title: "CRT Picture Adjustment Common Issues and Fixes"
pageid: 1089
revid: 3561
kind: explanatory_guide
source: "https://repair.wiki/w/CRT_Picture_Adjustment_Common_Issues_and_Fixes"
history: "https://repair.wiki/index.php?title=CRT_Picture_Adjustment_Common_Issues_and_Fixes&action=history"
permalink: "https://repair.wiki/index.php?oldid=3561"
last_edited: "2024-03-02T11:45:58Z"
contributors:
  - "ASRepairs"
  - "HaileyKitty"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for CRT Displays"
  - "Missing device page"
  - "Television/Monitors"
infobox:
  Device: "CRT Displays"
  Type: "Troubleshooting/Diagnostics"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# CRT Picture Adjustment Common Issues and Fixes

CRT (cathode ray tube) are found on older televisions, monitors, and other equipment.
![Inside of CRT television with basic components labelled.](images/f/f1/517px-CRT_diagram.jpg)

## Safety Warning:
CRT displays contain extremely high voltage (up to 30,000v!) and the acts as a capacitor which can store a lethal charge for weeks after the display has been unplugged. The tube **MUST** be discharged properly before performing any kind of internal repairs.

Here is a good guide to refer to for discharging CRTs: https://www.youtube.com/watch?v=1CVXzlkOjGg

CRTs also contain mains voltage so general electrical safety precautions should be taken when working on them.

## Service Manuals:
Due to the facts that most CRTs come from a time when repair was more common and companies didn't claim it was a security risk to have someone replace a failed capacitor, complete service manuals that included full schematics were often given out to independent repair shops, in the cases of older televisions they may have even been included with the television. Many of these manuals and schematics are now available online, simply look up the model of your TV/monitor and look for a service manual.

Descriptions and service manuals for Commodore monitors can be found here: [https://gona.mactar.hu/Commodore/monitor/Commodore_monitors_by_model_number.html Commodore monitors]

![An extreme example of misconvergence; all colors are fully separated.](images/7/75/Severe_misconvergence.jpg)

## Picture adjustment:
  - NOTE**: Most picture adjustments should only be done after it has been confirmed that there are no faulty components on the board and those that are faulty have been replaced.

  - WARNING:** For most of these adjustments to be effective, they must be performed while the CRT is turned on, make sure that you are isolated from ground and are using a nonconductive screwdriver to make adjustments. Stay clear of the neck board, anode cap, and exposed flyback circuitry whenever possible!

Over time, CRTs can go out of focus, misconverge, dim, or develop geometry issues; here is a very basic guide to troubleshooting and fixing such issues:

To start you are going to want a good testing image or program that can display images onto the CRT screen to aid you in adjusting focus or geometry. Here are some ways to do that:

- NEC test pattern generator is a program that will run on Windows and Linux (using Wine) and will generate test images onto your monitor for convergence, geometry, focus, and more.
- You can buy or make dedicated hardware that plugs into TVs or monitors and generates test patterns on the screen.
- You could burn a video calibration disc and play that onto the TV through a game console or DVD player. (Here is an example of one for NTSC TVs: https://archive.org/details/AvCalibrationNtscDvd)
- Some TVs or monitors may contain built-in test patterns that can be accessed through a service menu, check a service manual to see if they exist for your model and how to access them.

| Symptom/Issue | Adjustment/Fix |
| --- | --- |
| Images on screen appear blurry, particular at high resolutions. Is often caused by an out of focus CRT | Firstly, in the test pattern generator, go to the "Focus" or similarly named pattern, this will display a bunch of small dots on the screen, the goal of focusing the CRT is to make these dots as small and even as possible. Once the image is prepared it is time to begin making focus adjustments. Secondly, a magnifying glass may be helpful, particularly for small or high-resolution screens to be able to see the dot size better. Some very old CRTs may contain a focus adjustment potentiometer externally, either on the front or the back of the unit, however this is uncommon and this explanation is for CRTs with internal pots on or near the flyback. # Disassemble the monitor/TV, discharge the tube, and identify the flyback transformer and potentiometer locations. You may see 2 or 3 knobs on the side of the flyback transformer. In the case of a 2 knob transformer, they will be labelled "Focus" and "Screen" or something similar. In the case of a 3 knob transformer, they will be labelled "H Focus" "V Focus" and "Screen" or something similar. If there are no knobs on the side of the transformer then the adjustments may be discrete potentiometers located near the transformer, they will have similar naming on the PCB silkscreen. For this adjustment, you will only want to touch the focus potentiometers, do not touch the screen pot. # Turn the CRT on, ensure you are isolated from ground and using a nonconductive object to touch the potentiometers, dispand lay the Focus test pattern on screen using the highest quality connection available. # **For CRT with single focus pot:** Slowly turn the focus pot in a direction while looking closely at the dots displayed on scthe reen by the focus pattern. If the dots are becoming larger, then you need to turn the knob the other way. Once you have figured out the needed direction to turn the pot, look very closely at the dot and zero in on the point where the dot is smallest. **For CRT with dual focus pots:** When you have 2 focus pots you are looking for not only the smallest dot, but also one that is even in width and height. Begin with either the H or V pot and slowly turn while examining one of the dots displayed on the screen, zero in on the point where the dot is either shortest or thinnest depending on pthe ot you are adjusting. Once you have finished with one of the pots move ont o the next one. On the second pot ,you are looking not only to get the smallest dot,but also a dot that has an even width and height. Therefore after adjusting the second pot, you may need to return the first pot io make the 2 even. # Once you have gotten the focus to an optimal point, switch to a screen that is reflective of how you intend to use the CRT (game, desktop, movie, whatever) and ensure that the picture shows up well there and if applicable switch to the resolution that you plan to use the CRT at. # Once you have confirmed that everything is good, add a small amount of glue to the edge of each potentiometer to stop it from drifting in the future. Ensure that this is not extremely strong glue however in case you need to make adjustments again. |
| Screen is dim, colours not showing up well. | While in some cases a dim screen and lack of vibrant colours can be a sign of the phosphors on the screen degrading which is not fixable. This can be temporarily fixed by adjusting the brightness but will cause the screen to degrade at a quicker rate. Afterwards, I would also recommend verifying colours are correctly displayed after. Some televisions and monitors may contain external adjustments for brightness and contrast, however, if your CRT does have those or if the external ones do not suffice then here is how to adjust the internal screen pot: # Disassemble the monitor/TV, discharge tube, and identify the flyback transformer. Look for potentiometers on or near the flyback. You are looking for a potentiometer labelled "Screen" or "Brightness". Do not touch any of the other potentiometers. # Prepare an image to display on the CRT that contains a section with a lot of vibrant colours AND a large portion of pure black. Turn on the CRT and display this image, once the CRT is turned be careful of high voltage locations and try to only adjust the potentiometers using a non-c-nductive object. # Find which direction of adjustment increases the brightness of the pot then slowly turn it that way until the image is at a point where the colours are fairly bright and vibrant but not washed out. Pay attention to the black part of the image and ensure that it does not get any brighter, once the black part begins to get noticeably brighter then you have set the brightness too high and it should be turned back down. # Once you have confirmed that everything is good, add a small amount of glue to the edge of the potentiometer to stop it from drifting in the future. Ensure that this is not extremely strong glue however in case you need to make adjustments again. The "optimal brightness and vibrancy" will be different for different people so it is hard to give an exact measure of where it should be. it is important to note that having the screen too bright can increase the speed in which the phosphor degrades to the point where no amount of adjustment can bring the brightness or colour back. If this adjustment was done when the phosphor was already starting to go then it may work as a temporary fix but it will not last forever. |
| Misconvergence, one colour sticks out from the rest on edges between light and dark, or in extreme cases the colours have completely separated from each other. | Information coming soon |
| Tilted Image, the whole image appears to be slightly (or in rare cases drastically) tilted. | Issues like this often stem from physical abuse of the display causing the deflection coil assembly to loosen and twist. The deflection coil is responsible for bending and moving the straight beam of the electron gun(s) in a way that creates the picture on the screen, it does this magnetically so if it is physically tilted then the whole image on the screen will appear to be tilted. Most modern CRT monitors and TVs will have some form of tilt correction in the OSD. On monitors it is typically in the user settings while on TVs you may have to access the service menu (Refer to mthe anual on your TV for how to access.) In the case of there only being a small tilt in the display then using these adjustments is a good way to correct it. These adjustments are also a good way to fine-tune after making a physical adjustment. Not all displays have the tilt correction setting or the tilt correction may not be working/not be enough to correct the tilt on your display. For this, you can make a physical adjustment to the deflection coil assembly. # Take note of the direction and severity of the tilt of the screen. # Open the display and discharge the tube. # Loosen the screw that holds the deflection coil assembly, this screw is located at the back of the deflection coil assembly and is normally the very last object around the neck of the tube before it reaches the socket. # Make a rough adjustment to the tilt of the deflection coil based on what you observed from the tilt of the screen. Remember that the deflection coil basically aims the electron gun so if you tilt it to the right, th'e electrons path will tilt to tWt. Since when viewing the screen you are looking at an inverted view of how the electrons hit the screen. Here is a visual to help understand how the gun adjustment works:https://youtu.be/pjTtwBO7UIo # Turn CRT on to display an image and check for tilting. As long as the tilt is very minor, you can be fine tuning. If you have available OSD controls then you could do the last fine-tuning on the OSD, if you do not have OSD controls or if you just want to have the coil as perfectly aligned as possible then you can see the steps for physical fine-tuning: ## Put an image on screen that has a straight line close to the top or bottom bezel of the display, you can use this as you gaurge for tilting. ## Ensure the deflection coil screw is tight enough hold the coil place while still being slightly twistable. ## Being extremely careful of the neck board and any exposed wiring on the deflection coil assembly. Begin making slight adjustments to the tilt of the deflection coil, after each adjustment check the line parallel with the bezel. # Once the tilt has been corrected to your satisfaction, re-tighten the screw then put the display back together. If your display has tilt correction in the OSD then any further small adjustments can be made in the OSD. |
