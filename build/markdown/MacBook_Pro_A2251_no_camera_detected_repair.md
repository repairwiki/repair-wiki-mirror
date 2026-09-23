---
title: "MacBook Pro A2251 no camera detected repair"
pageid: 77
revid: 523
kind: repair_guide
source: "https://repair.wiki/w/MacBook_Pro_A2251_no_camera_detected_repair"
history: "https://repair.wiki/index.php?title=MacBook_Pro_A2251_no_camera_detected_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=523"
last_edited: "2023-10-29T15:28:31Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Stubs"
infobox:
  Device: "MacBook Pro A2251"
  Affects_parts: "Motherboard"
  Needs_equipment: "multimeter, soldering iron, soldering station"
  Type: "Soldering"
  Difficulty: "3. Hard"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# MacBook Pro A2251 no camera detected repair

## Problem description
Addressing issues with a MacBook (820-01949) not detecting the camera.

## Symptoms
- Camera not detected
- Possible burned or exploded L8504 filter on TCON board

## Solution
### Repair Steps
![L8504 (Figure 1) -- No image yet. Help expand this page by uploading it](images/3/30/Placeholder_image.jpg)

#### Check L8504 Continuity
- Use a multimeter in continuity mode to check L8504 (Figure 1).
- Normal reading should be close to 0.01.
- If L8504 is blown or burned, proceed to the "L8504 blown or visibly burned repair steps" below.

#### Test with Known Good Display
- Verify camera function using a KNOWN GOOD display assembly.
- If the camera works with a different display, the original display might be faulty.
- Make sure to check L8504 before diagnosing the display issue.

### Repair Steps
#### Camera Works with Known Good Display
- If camera works with a known good test display, replace the display assembly.
![R5610 (Figure 2) -- No image yet. Help expand this page by uploading it](images/3/30/Placeholder_image.jpg)

#### L8504 Blown or Visibly Burned
- Understand that L8504 failure indicates a catastrophic short within the TCON board of the display or a melted/corroded display cable/connector.
- Repair L8504 only after addressing the display issue, as L8504 might fail again if the display issue persists.
- When replacing L8504, address corresponding pad and trace damage.
- Use 36 or 37 AWG enamel coated copper wire for jumper wires due to webcam and ambient light sensor power requirements.
- Connect jumper wire from the input side of the filter (PP5v_G3S) to R5610 (Figure 2) or a suitable point.
- Apply conformal coating to jumper wire.
- Use a 120 Ohm ferrite filter rated for 1.5 amps (402 package size).
- After replacing L8504 and addressing trace issues, replace the display assembly or repair it by replacing damaged cables/connectors.

#### No Camera Function, L8504 Normal
- Attempt to restore T2/BridgeOs firmware via Apple Configurator 2 by entering DFU mode.
- Ensure your Mac is on the latest macOS version.
- Follow Apple's support article on [https://support.apple.com/guide/apple-configurator-mac/revive-or-restore-an-intel-based-mac-apdebea5be51/mac reviving or restoring T2/BridgeOs firmware].
- If no camera function after firmware revive, and other causes are ruled out, U8504 might be faulty, or there could be trace/resistor issues between the camera connector/U8504 or between U8504 and the T2 chip.
- A hardware issue with the T2 chip might also cause camera detection problems.
