---
title: "2010 A1286 MacBook Pro Missing PM SLP S4 L repair"
pageid: 2670
revid: 5311
kind: other
source: "https://repair.wiki/w/2010_A1286_MacBook_Pro_Missing_PM_SLP_S4_L_repair"
history: "https://repair.wiki/index.php?title=2010_A1286_MacBook_Pro_Missing_PM_SLP_S4_L_repair&action=history"
permalink: "https://repair.wiki/index.php?oldid=5311"
last_edited: "2024-11-26T01:15:11Z"
contributors:
  - "XTA"
anonymous_edits: 0
categories:
  - "Repair guide"
  - "Repair guides for MacBook Pro A1286"
  - "Stubs"
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# 2010 A1286 MacBook Pro Missing PM SLP S4 L repair

## Problem description
2010 820-2850 or 2010 820-2849 missing PM_SLP_S4_L and therefore doesn't boot.

![PCH (U1800) and SMC (U4900) on a 820-2850](images/6/6c/Eec97256e15786cf5cbc9e0322cb16f5.png)

## Symptoms
- PP5V_S3 & PP3V_S3 missing (Not short) because PM_SLP_S4_L is completely missing (not pulsing) and therefore the device does not boot.
- Green light missing PM_SLP_S4_L
- Dim green light missing PM_SLP_S4_L

## Solution
Unfortunately many and normally it's going to come down to SMC or PCH in the case of no liquid damage which is why this guide is marked specialist.

### Diagnostic Steps
Okay so I am going to start by saying this, this problem is sometimes a never ending rabbit hole, once I had a board where to fix this issue I had to run a jumper to J6900, replace the SMC and replace the PCH just to restore PM_SLP_S4_L, this is probably very rare to run into but most of the time we are looking towards BGA rework to fix this. This problem takes 90% diagnostics and 10% actual repair and has a lot of details we need to go into.

So there are 2 types of this issue you can have, dim green light on charger or full green light on charger, this here is a MAJOR hint and it's important to use this hint as aforementioned this issue has many causes.

Lets start with **dim green light on charger**. This signifies the issue is related to either 1-Wire or SMC.

So first things first, lets see if this issue is SMC related since you can do this before removing the logic board and is the easiest thing to test. To test this we want to attempt to boot the device in SMC Bypass mode, this can be achieved by removing the battery and adapter, holding the power button down and while maintaining holding the power button down plug a genuine 85w MagSafe adaptor in (Must be 85w, these boards won't boot without battery on a 65w or below charger), maintain clicking the power button for another 5 seconds and let go, if successful the fans will start spinning very fast and the machine will boot (Don't rule this out with one try, sometimes you have to try multiple times to get SMC bypass mode to kick on). If you are able to get the machine to boot in bypass mode, we now know for sure the issue is SMC related.

However if you do not get the machine to boot in SMC bypass mode and have a dim green light, bad luck my friend! Likely dead PCH in combination with dead SMC, You can check for missing or low ADAPTOR_SENSE at pin 5 of J6900 (top pin, DC-in board connector), sometimes this is as simple as replacing U6900, on rare occasions it's trace damage and ADAPTOR_SENSE is present at U6900 pin 5 and can be jumped around the board to J6900 pin 5 to get the green light back however this isn't going to fix your PM_SLP_S4_L issue because we completely negated and bypassed this signal and still nothing, If in this case you get the green light back follow the instructions for green light, missing PM_SLP_S4_L. If you don't get a green light you still have a chance it's the SMC. If the green light doesn't come back you want to try boot the machine in SMC bypass mode while already having probes on PP5V_S3 and then PP3V3_S3, if these signals are low (not missing, low), you need to try address what's pulling them low by manually enabling PP5V_S3 by running a jumper wire from C7831 (side 2), remove (or disconnect from top pad) R7912 and solder the jumper wire on the top pad to manually enable PP5V_S3 in a S5 state that way you can hunt the short pulling it low to try address it and then try once again to boot the machine in SMC Bypass mode, if you are able to successfully do so, then follow the next set of instructions. If they are completely missing, to cut it straight with you probably have both a dead SMC and PCH or PCH related issue and dead SMC, you may be able to fix the PCH issue using the green light no PM_SLP_S4_L set of instructions and then get the board booting into SMC Bypass mode and then address the issue as though it's once again dim green light boots in SMC bypass mode. However as I said, fun rabbit hole that might never end!

Okay so in the case we do get boot with SMC Bypass mode with a dim green light, 7/10 dead SMC 1/10 crap under the SMC that can be fixed with a flux and reflow treatment, 1/10 corrosion on the SMC VCC caps stopping it from powering on or 1/10 dead U6900 pulling ADAPTOR_SENSE low. Now if you get either of the 3/10 you need to buy a lottery ticket but I pointed you there so you need to split the winnings! You have nothing to lose attempting to reflow the SMC so might as well! It either works and you are happy or it doesn't and you are replacing it anyways. However we are going to operate on the assumption your not that lucky and the SMC is dead, time to pull one off a donor, reball it and solder it on, You need an exact donor board, like the EPROM, these chips are programmed specifically for the device they are on, so a new one won't cut it and one off anything but another 820-2850 isn't going to work, once done it should now work!

Lets move on to the dreaded **green light no PM_SLP_S4_L**

I am going to tell you from the start, this one is no fun! Normally just dead PCH in the case of no liquid damage. They say "anything but the chipset/PCH" but they lie ;(

You can still give SMC Bypass mode a try but it's almost certainly not going to do anything. Get that board out of it's shell!

Okay so we **almost** know for CERTAIN it's not your SMC, I did say almost because it still could be but in this case it's pretty rare for it to be the SMC. Let's try rule that out.

So a pretty quick way to do so is to test for SMC_ADAPTOR_EN without the battery connected, this can be checked at R5085 (top side), it should be 3.42V, this signal act's as your high low high pulse that PM_PWNBTN_L would normally create when you push the power button in the case you boot with no battery. This signal tells the PCH that you want to turn the device on so without it, you won't get PM_SLP_S4_L. If the board does boot with no battery off adaptor only and power button does nothing on a good keyboard, it's likely related to this SMC issue. If you are missing SMC_ADAPTOR_EN, shotgun replace Q7920 and R5085 and hope that changes, in this case you are more prone to having crap under the SMC causing this or cracked solder balls on the SMC from a drop, you can attempt to reflow the SMC and hope this issue goes away otherwise replace the SMC. If you have 3.42v on SMC_ADAPTOR_EN and green light on the charger your SMC is good which isn't good news!

So moving forwards we now have ruled the SMC out of the picture, this is a PCH issue. There are some things you need to understand about how the PCH works and what you need for it to give you the sweet PM_SLP_S4_L signal that enables the S3 rails.

On this board we need:

RTC_RESET_L -  Bypassed on this board, PP3V42_G3H in this case

PCH_SRTCRST_L - Made from PP3V42_G3H

PCH_INTVRMEN_L - Made from PP3V42_G3H

PPVRTC_G3H - Bypassed on this board, PP3V42_G3H in this case

PCH_CLK32K_RTCX1

PP3V3_S5

PM_RSMRST_L

PM_BATLOW_L

PM_PWRBTN_L or SMC_ADAPTOR_EN - Likely SMC_ADAPTOR_EN in our case since we don't have a battery connected while we diagnose the board.

PP3V3_SUS - Bypassed on this board, PP3V3_S5 in this case.

Now missing just one of these signals can mean no PM_SLP_S4_L for you! So we already checked SMC_ADAPTOR_EN, that's okay. Let's check out those bypasses! So we know we have PP3V42_G3H because we wouldn't have our green light without it but we want to check out if it's making it's way to the PCH. In the case of PPVRTC_G3H (Not actually a signal name used on this board but it is on most other boards so we are just going to call it that), you just need to check if you have 3.42V on pin 1 of C2421, C2420 and C2422 if you do, the PCH is getting the RTC signal! PCH_SRTCRST_L can be tested at R1802 or C12802 it should be 3.42V, if it's low replace both the resistor and cap, very likely will be there, PM_RSMRST_L is at R1825 likely won't be there, not needed for boot. PCH_INTVRMEN_L can be tested at R1800, you really need this signal as the PCH won't even power up without it, it should be there replace R1800 if not, RTC_RESET_L is at R1803 and C1803, if it's not there shotgun replace both should come back. PM_BATLOW_L should be 3.3v side 2 at R1931 if not replace it. PP3V3_SUS (not called that on this board since it's bypassed but we are going to stick with that name) should be at C2425 at 3.3V.

If you have all of them last thing to check is PCH_CLK32K_RTCX1, you will need an oscilloscope for this, you need to test for a 32k signal at side 2 at R2810, if it's not there make sure R2810 is 0 ohm, if it is, replace Y2810 to restore the clock signal.

Okay so if you've made it this far, you have all of them and haven't found your issue yet, time to get your coldplay songs out, PCH dead! Attempt reflow or get ready to replace it!

Now I have listed almost every single possible cause and every single thing to look for, I am sure there could be some very rare issue I haven't touched on but in my opinion if this guide cannot lead you to the problem, you are in way to deep now and likely will be chasing this problem for a very long time before you figure it out, even I know to much about this issue. Unless the board is a 640M this board is worth maybe $50? Even in the case of a 640M it's worth maybe $100-$150 and you are probably just better off swapping the CPU to another working board and transferring the serial stickers and clean the ME region and change the serial number on the ROM. (It will genuinely be easier). The only time I might dig deeper is for an 820-2849, even then you have to set a limit or you will be chasing this issue the rest of your life. It's entirely possible you have internal layer damage on the board and are getting PM_SLP_S4_L but only in one place and it's originating point is only in ONE place which is under the PCH in the BGA so your going to have to remove the PCH to get it anyways at which point do you call a dead board a dead board?

Repair steps have disappeared but we are specialists ;) we don't need them and I've already told you what to look for and replace, if you know how to replace an SMC, you know how to replace an SMC, if you know how to replace a PCH you know how to replace a PCH. Me giving you steps isn't going to help you because BGA and especially fpBGA requires practical experience, most of you are going to delaminate a PCH, the board or solder on an SMC sideways if I give you steps, practice and learn on donors and come back to this one.

I've written this guide out for repair preservation, as a resource to help people learn the basics of PM_SLP_S4_L, where it comes from and how to get it back (Some of the fundamentals here can be applied to other boards) and for people like me who still like these boards and on the off chance the rare 640M boards become worth a lot in the future! Most of the time this repair isn't worth doing, we know that!
