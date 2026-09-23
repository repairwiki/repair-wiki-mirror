---
title: "MacBook Pro A2338 Audio Not Playing From Internal Speakers"
pageid: 2417
revid: 4923
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2338_Audio_Not_Playing_From_Internal_Speakers"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2338_Audio_Not_Playing_From_Internal_Speakers&action=history"
permalink: "https://repair.wiki/index.php?oldid=4923"
last_edited: "2024-09-24T06:02:32Z"
contributors:
  - "ASRepairs"
  - "Samsscreenrepair"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A2338"
  - "Stubs"
infobox:
  Device: "MacBook Pro A2338"
  Affects_parts: "Motherboard, Speakers"
  Needs_equipment: "Microscope, Soldering Iron, Hot Air Station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2338 Audio Not Playing From Internal Speakers

## Problem description
When trying to play audio of any kind through the internal speakers, no sound is produced. YouTube produces an "audio renderer error" and advises restarting the computer. Other videos with audio do not play properly. When connected to bluetooth audio, all functions work as intended.
![Example image (Figure 1) -- No image yet. Help expand this page by uploading it!](images/3/30/Placeholder_image.jpg)
## Symptoms
- No audio from internal speakers
- Videos with audio crashing or not playing properly
- No chime on startup
- Bluetooth audio working as intended

## Solution
The solution was to solder the loose CR732 capacitor back onto the board.

### Diagnostic Steps
![CR732 Boardview](images/a/ae/CR732.png)
I began by isolating all audio-related components from the board - both speakers and the headphone jack flex. Videos would still not play properly. The next step was to conduct a visual inspection of the board under the microscope. Suspect areas were around UR500 Audio Codec, and all four speaker amp ICs UR700, UR730, UR600, and UR630. Upon visual inspection, I noticed that there was a loose capacitor near UR730. I checked the boardview and schematics to determine that this was CR732 on the SPKRAMP_E_DREG line.
### Repair Steps
I removed CR732, tinned the pads, and soldered it back onto the board using hot air and leaded solder. Audio played normally after reassembling.
