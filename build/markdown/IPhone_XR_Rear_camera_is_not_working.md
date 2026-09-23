---
title: "IPhone XR Rear camera is not working"
pageid: 3840
revid: 6715
kind: repair_guide
source: "https://repair.wiki/w/IPhone_XR_Rear_camera_is_not_working"
history: "https://repair.wiki/index.php?title=IPhone_XR_Rear_camera_is_not_working&action=history"
permalink: "https://repair.wiki/index.php?oldid=6715"
last_edited: "2025-05-14T19:10:38Z"
contributors:
  - "Samhext"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for IPhone XR"
  - "Stubs"
infobox:
  Device: "IPhone XR"
  Affects_parts: "Motherboard, Rear camera"
  Type: "Soldering, Part replacement"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# IPhone XR Rear camera is not working

![Take notice of the orientation dot](images/b/b3/XR_Rear_Cam_LDO_U1601.png)

## Symptoms
- Rear camera doesn't work. Just shows black screen
- Front camera is working

## Solution
- First step would be to try replacing the rear camera with a known working part
  - You may need to flash an update to get the rear camera to work
- If new rear camera does not fix issue, Diode Mode the Rear Camera Connector
  - Check for any shorts or Open Lines (OL)
- Check the LDO U1601. This is a power rail for the camera
  - **IMPORTANT**: Check orientation of the LDO from the actual board. ZXW shows Pin 1 incorrectly, so orientation is wrong. (see image for correct orientation)
  - See if this LDO is loose or broken.
  - Or just try replacing it & see if rear camera starts working.

Migrated from old wiki
