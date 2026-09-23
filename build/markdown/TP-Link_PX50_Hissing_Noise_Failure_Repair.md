---
title: "TP-Link PX50 Hissing Noise Failure Repair"
pageid: 9809
revid: 14209
kind: other
source: "https://repair.wiki/w/TP-Link_PX50_Hissing_Noise_Failure_Repair"
history: "https://repair.wiki/index.php?title=TP-Link_PX50_Hissing_Noise_Failure_Repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=14209"
last_edited: "2026-03-28T02:44:58Z"
contributors:
  - "M32"
anonymous_edits: 0
categories:
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# TP-Link PX50 Hissing Noise Failure Repair

The TP-Link PX50 is a PLC+WiFi mesh router. It uses cheap consumer grade capacitors and passive convective cooling. This results in the device cooking itself if placed in a location with poor airflow.

A symptom of impending failure is a hissing noise coming from the device especially when PLC backhaul is active. Eventually the device will fall off the network and the status LED may turn red.

This repair involves replacing two low ESR 16v 680uF electrolytic capacitors.

  - Equipment needed:**
- soldering iron
- solder
- snips to trim capacitor legs
- philips #2 screwdriver
- flathead screwdriver or paint can opener

  - Supplies needed:**
- replacement capacitors (I used Nichicon [https://www.digikey.com/en/products/detail/nichicon/UHE1C681MPD/589265 UHE1C681MPD])
- replacement silastic (I used Chip Quik [https://www.digikey.com/en/products/detail/chip-quik-inc/EGS10W-20G/10059589?gclsrc=aw.ds&gad_source=1&gad_campaignid=20232005509&gbraid=0AAAAADrbLlhNC2cu46g5_jXU1zrLhATmB&gclid=Cj0KCQjw1ZjOBhCmARIsADDuFTAABEoUnra0ugbv1TmxxXgIA-42TKSB_deTrtshbe2V4vPNEC9d9 EGS10W-20G])

Step 1. Pry open the top cover. The cover is held on with 4 plastic clips (located at approximately the red circles in photo below). The main body can be squeezed by hand slightly to relieve some pressure from an opposing set of clips and the cap can be pried up in those spots with a flathead screwdriver inserted in to a vent opening (a paint can opener works great for this as it allows you to pull up on the lid without putting pressure on the lip of the main body).
![Location of tabs top view](images/e/e3/IMG_0914.jpeg)

Step 2. Unscrew two Philips screws holding the PCB assembly within the body shell. Use a Philips #2 screwdriver to remove the two screws (circled in blue below).
![View with top cover removed.](images/5/54/IMG_0913.jpeg)

Step 3. Extract the PCB assembly. Pull the PCB assembly straight out.

Step 4. Locate the bulging electrolytic capacitors and remove. The capacitors may have some silastic adhering them to each the board and each other. The silastic is likely dry and no longer sticky at this point. Carefully break it away and discard while being very careful not to rip or knock off any of the microscopic surface mount components nearby. Desolder and discard the failed capacitors. Location of capacitors that failed for me are circled in red below.
![TP-Link PX50 hissing capacitors.](images/2/20/IMG_0909.jpeg)

Step 5. Install replacement capacitors. Clean the pads and insert the replacement capacitors, seating them against the PCB. Negative (longer) leg of each goes to the outside edge of the PCB. Solder on the capacitors, being mindful of the small SMDs nearby. Trim the legs and apply fresh silastic between the capacitors and anchoring them to the PCB.
![Replacement capacitors installed with silastic](images/7/74/IMG_0911.jpeg)

Note: The replacement capacitors I used are a slightly taller form factor and a little wider leg spacing but worked with no problem since there is enough room in the case.
![Capacitor comparison. Originals on left.](images/d/da/IMG_0908.jpeg)

Step 6. Power on to test. It may take a couple minutes to rejoin the network, but the hissing sound should be gone immediately.

Step 7. Reassemble. Ensure the ports line up with the case opening (circled red below) and the opposite edge of the PCB is retained in the provided slot (circled blue below).
![PX50 empty case.](images/1/1b/IMG_0912.jpeg)
Reinstall the screws and the cap, ensuring the different sized pegs on the cap go into the appropriate holes (circled green below and in photo for step #2 above).
![Bottom view of TP-Link PX50 top cover.](images/2/21/IMG_0910.jpeg)
If any clips were broken during opening you may choose to put a dab of silastic in the same spots to retain the lid. Only a couple of intact clips are needed to keep the lid attached in most instances.
