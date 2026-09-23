---
title: "Pixel 6a Vibration and Haptics Not Working"
pageid: 6704
revid: 12212
kind: repair_guide
source: "https://repair.wiki/w/Pixel_6a_Vibration_and_Haptics_Not_Working"
history: "https://repair.wiki/index.php?title=Pixel_6a_Vibration_and_Haptics_Not_Working&action=history"
permalink: "https://repair.wiki/index.php?oldid=12212"
last_edited: "2025-10-02T04:38:38Z"
contributors:
  - "VCCBoardRepairs"
  - "Cheapskate777"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for Pixel 6a"
infobox:
  Device: "Pixel 6a"
  Affects_parts: "Main Logic Board"
  Needs_equipment: "Screwdrivers, spudger, tweezers"
  Type: "Teardown"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Pixel 6a Vibration and Haptics Not Working

  - Pixel 6a Vibration/Haptics Not Working**

The device's haptics do not register notifications, button presses, etc. This guide realigns the pins for a better contact between the motherboard and haptics component.

🔍 **Step-by-Step Diagnosis**

If your vibration motor is not working, hard reset the phone by holding down the power button + volume up key for 30 secs.

If the vibration comes back after reboot and dies later, your device may benefit from this guide.

The vibration motor usually dies after quick key presses. Some users say that it dies when connected to a weak cellular connection.

Check for similar kernel logs hinting that the vibration motor is not working
 [09-06 20:10:22.074 1222:27231 E/android.hardware.vibrator-cs40l26] Polling error or timeout! (0)

 [09-06 20:10:41.948 1222:27563 W/Vibrator] Failed to get state "Haptic"

 [09-06 20:07:05.492 1314:1445 E/NotificationVibratorHelper] Error creating vibration waveform with pattern: [0]

 [09-06 20:05:03.736 1314:1668 E/VibratorController] Vibrator HAL on failed: Status(-5, EX_ILLEGAL_STATE): ''
💡 **Issue with Vibrator Contacts**

The vibrator is not firmly attached to the motherboard like other "lego" style connectors. The motherboard has spring loaded pins that press against the vibrator module. After time, I believe the contacts lose their elasticity and make a poor connection, causing many kernel errors. After too many errors, I think the phone locks out the vibrator to prevent further damage to other components.

  - ⚙️ Hardware Solution**
![Red circle is over vibrator contacts](images/3/34/Pixel6a-vibrator-overview.png)
1. Take off the screen and midframe
1. ![Very gently bend both contacts upwards so that they rest closer to the midframe](images/e/ee/Pixal6a-vibrator-bend.jpg)
1. ![If needed, slightly bend the contacts on the vibrator downwards so that the pins are closer to the motherboard](images/5/50/Pixel6a-vibrator-bend2.jpg)
1. You should feel some tension when screwing back the midframe as the pins press against each other.

💬 **External Discussion for this Issue**

- https://github.com/GrapheneOS/os-issue-tracker/issues/2414
- https://discuss.grapheneos.org/d/11507-haptic-feedback-randomly-crashes
- https://old.reddit.com/r/GooglePixel/comments/13pfli3/pixel_6a_vibration_stops_working_randomly_comes/
