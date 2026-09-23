---
title: "Samsung Galaxy A03s CPU Swap Step by Step Guide"
pageid: 2202
revid: 5067
kind: explanatory_guide
source: "https://repair.wiki/w/Samsung_Galaxy_A03s_CPU_Swap_Step_by_Step_Guide"
history: "https://repair.wiki/index.php?title=Samsung_Galaxy_A03s_CPU_Swap_Step_by_Step_Guide&action=history"
permalink: "https://repair.wiki/index.php?oldid=5067"
last_edited: "2024-10-14T01:31:55Z"
contributors:
  - "ASRepairs"
  - "VCCBoardRepairs"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for Galaxy A03s"
infobox:
  Device: "Galaxy A03s"
  Type: "Method"
  Difficulty: "4. Specialist"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Samsung Galaxy A03s CPU Swap Step by Step Guide

## Problem description
If you have a Samsung A03s that does not boot up, and all other efforts to fix the existing board has failed, then you can follow this guide on how to swap the paired chips onto another working board for the purposes of recovering the data that's trapped inside the chips.

🚨 Please Note 🚨

This process is super risky & requires tons of practice & skill to successfully do it.

If you damage the CPU or the UFS (Storage) chip, then it's game over. The data is gone forever.

So do not try this if you have no experience with CPU Swaps.

Absolutely DO NOT try this if you have no microsoldering experience.

I would recommend you practice on donor motherboards & once you can do it successfully 3 in a row, then you should have enough experience to do this on a live customer's board.

## Recommended Tools
Hot Air Station: Atten ST-862D with 13mm Bent Nozzle

Soldering Iron: Aixun T420D with T210 Handle & JBC C210018 Knife Tip

## Symptoms
- No Power
- Does not boot up
- No signs of life
- Board is cracked
- Board is water damaged beyond repair

## Solution
### Repair Steps
First, you need to locate the CPU and UFS.

- CPU holds the encryption keys
- UFS has the data, but it's encrypted

Both chips MUST be fully working & not damaged/cracked.

These chips talk to each other & during bootup, they exchange the keys so the phone can decrypt the data after the pin code is entered. Without the pin code, data cannot be decrypted & accessed.

Here's a picture of where these chips are:
![819x819px](images/d/d2/A03s_Back_of_Board.png)

Typically, these are next to each other & very large chips. They also tend to have thermal paste or thermal pads. Sometimes they have shields completely covering them.

On this model, the CPU is labeled as MediaTek. So we can assume the other chip is the UFS.
![712x712px](images/0/08/A03s_CPU.png)

Now we must remove the shield around it to access the chips. I would recommend adding 138C Ultra Low Melt solder to the solder joints where the shield is attached to the board. Make sure to add plenty of flux & use a knife tip style iron

This will make removing the shield much easier
![669x669px](images/2/29/A03s_Shield.png)

Using high temps, like 400C/60 air, heat around the perimeter

Use a hook tool or tweezers to grab onto the shield & pull it up, until it detaches, like this:
![696x696px](images/3/3c/A03s_cpu_shield_removed.png)

And now you have clear access to the 2 chips you need.
![687x687px](images/d/da/A03s_CPU_&_UFS.png)The CPU and UFS chips have hard & rubbery "glue" like substance that has these chips sealed to the board. This stuff is called "underfill". It must be cleared out with a sharp blade, like Scalpel #11 blade.
![641x641px](images/2/2c/Scalpel.png)
Go around all 4 sides of the CPU and UFS & get rid of it. This makes it so you can lift the chips easiest.
![798x798px](images/0/04/Underfill.png)
Switch to the largest nozzle your hot air station can support. For the Atten, we are using a bent 13mm nozzle
![828x828px](images/a/a4/Large_nozzle.png)
You're also going to need a very thin spatula blade. Use sandpaper to thin it out even further. Ideally, you'll want to taper the tip. This allow the blade to enter under the chip safely & cut through the underfill
![988x988px](images/9/93/Thin_blade.png)
You'll want to use around 380C-400C to heat the chip in a circular motion. Make sure to start off far away, about 6in and heat in circles. This is to first warm up the board.

Over a 30 second period, get closer & closer until you're about 2-4mm away and always keep moving in circles.
![882x882px](images/6/60/Heat_cpu.png)
After about 30 seconds, the board should be very hot. This will make the underfill very soft.

Make sure to keep heating the IC in circles while still in close proximity.

Find an entry point, where there's no components and gently try to pry into the chip. But only go in horizontally. Maybe a little angled to try to get under, but stay as horizontal as possible

If you don't feel it budge, then don't force it in. Although some force is required, there's a fine point on what's too much. This is where lots of practice comes in to know what proper force is
![807x807px](images/8/83/Enter_spatula.png)

.As the spatula starts entering, do slicing motions, in and out. But do it gently.

You should be at about 60-90 seconds into this by this point.

If you're not having luck entering under the chip, try turning your temps & air flow up by 10 points and try again.

Don't heat the chip more than 2 or 3 minutes at a time. Reasses the situation & see if you need to adjust your temps more. If your tool is too thick. If maybe there's a better spot to enter.

Whatever you do, do not bend the chip up trying to remove it. You can damage it permanently & lose all chance to get data.
![759x759px](images/9/9e/UFS_removed.png)
Once the chip is removed, inspect it for any damage. Look closely for any ripped pads or any scratches on the IC. This is where most go wrong & damage the chip. In many cases, if the chip gets damaged, then it's game over.
![Using a thin blade, we heat the CPU and gently slide the blade between the board & the chip](images/5/52/Cpu_removal.png)
Then you'll have to repeat the same steps to ultimately remove the 2 important chips: CPU and UFS
![A03s CPU on board with UFS removed](images/b/b7/A03s_CPU_on_board_with_UFS_removed.png)
![CPU and UFS removed](images/e/ef/CPU_and_UFS_removed.png)
Make sure to save these 2 chips. They are paired together & must be installed onto the working donor board. I would suggest to have a designated spot on your bench, like a small tin can or box, where you will always place the critical customer chips into, so you don't mix them up with the donor board chips.

Then, we must prep the donor board.

Start by removing the same 2 chips, but this time, we are saving the board & throwing away the CPU and UFS from the donor board.

![Wicking donor board](images/4/40/Wicking_donor_board.png)
After removing the chips, we must prep the board.

Using hot air at 250C / 40 air flow, pick off all the big chunks of underfill off the board. You can use your tweezers, scalpel blade or other pointy tool to pick it off. The hot air will soften it so it comes off really easy.

Then you want to add tons of flux on the board & run your iron with a big blob of low melt solder (138C), over all the pads. Make sure all pads get covered with the new solder.

Make sure to clean the board thoroughly with iso and toothbrush.

Now, add tons of flux again & wick all the pads flat. Then clean the board again.
![Cleaning pads & board](images/f/f6/Cleaning_pads_&_board.png)
Repeat this for both CPU and UFS pads. Make sure every speck of underfill is removed. This will ensure the chips sit evenly & flat.
![Clean A03s board with no underfill](images/d/d0/Clean_A03s_board_with_no_underfill.png)

Next step is to prep the customer's chips: CPU and UFS
![UFS Chip on micro jig](images/8/85/UFS_Chip_on_micro_jig.png)
Use a jig, like the 2uul Micro Jig, to hold the IC facing up. As it makes it easier to work on the chip. We have to clean off all the underfill, prep the pads & wick them flat.
![Prepping UFS pads](images/b/bd/Prepping_UFS_pads.png)
Add lots of flux then use 138C low melt solder to run over all the pads.

Then add more flux & do it again.

The goal is to clean off as much of the underfill as possible.

You can use hot air & a scalpel blade to pick off any small remnants of underfill, if necesary.
![Removed a lot of the underfill](images/5/59/Removed_a_lot_of_the_underfill.png)
And make sure to clean off all the burnt flux regularly using iso & q-tips.
![Wicking UFS chip pads](images/2/2c/Wicking_UFS_chip_pads.png)
Lastly, you'll want to wick the chip flat. This allows for better results when reballing a large IC like CPU and UFS.

Repeat the same steps for the CPU.
![Add paste to the pads](images/6/62/Add_paste_to_the_pads.png)
If the chip has a lot of oxidized pads (pads that are dark gray & are not taking in any solder), you can use try this trick.

Add flux & solder paste to the chip
![Spread the paste on the CPU](images/6/6c/Spread_the_paste_on_the_CPU.png)

Make sure to spread it across the whole chip
![Hot Air the solder paste on the pads](images/1/11/Hot_Air_the_solder_paste_on_the_pads.png)
Then use hot air to melt the solder at 320C / 25 air.

Once the solder paste has melted & turned into solder balls, you can run your iron over all the pads.

You'll see a bit portion of the oxidized pads are gone.
![Wick CPU Pads](images/2/2b/Wick_CPU_Pads.png)Then you can wick all the pads flat

And clean the chip with iso & a toothbrush
![Cleaning the edge of the CPU](images/6/68/Cleaning_the_edge_of_the_CPU.png)
Once you remove the chip from the chip holder, you'll find that there's lots of gunk on the edge of the IC.

An easy way to clean all this off, is to use a scalpel blade and run along the edge of the IC. Make sure to do all 4 sides.

Once the IC is super clean on all sides, we can start the reball process:
![MT6765V CPU and Stencil](images/f/f9/MT6765V_CPU_and_Stencil.png)
First, you need to have the right stencil. Best way to find it, is to search the CPU model number. In this case, we needed a MT6765V stencil.
![CPU and Reballing Paste](images/f/f8/CPU_and_Reballing_Paste.png)
For CPU reballing, using Mechanic XG-50 183C paste works very nicely

Using a metal spatula, scoop up a small bead of paste, about the size of a pea.
![Reballing paste on the spatula](images/7/73/Reballing_paste_on_the_spatula.png)
Since it's very watery, you must dry out the paste so it can give you a better reballing result.
![Paste drying technique](images/8/81/Paste_drying_technique.gif)
You'll want to get a clean cloth or paper towel & press the paste into it. You'll want to do this enough until the paste is more of a matte color than glossy.

In the end, it should look more like this:
![Dried out reballing paste](images/0/06/Dried_out_reballing_paste.png)
Now, you're ready to actually reball.

Place the IC on the clean cloth or paper towel, as this provides a soft cushioned surface for the IC, and place the stencil on top.

Make sure to line it up perfectly
![CPU under the stencil](images/a/a2/CPU_under_the_stencil.png)
Using 2 fingers, press down on the stencil
![Holding stencil down with 2 fingers](images/7/7b/Holding_stencil_down_with_2_fingers.png)
Then spread the dried out paste over all the pads
![Spread the paste](images/d/d1/Spread_the_paste.png)
Make sure to fill every hole.

Do multiple passes over the whole chip, so the paste is packed into every hole.
![Paste applied to the stencil](images/0/00/Paste_applied_to_the_stencil.png)
Then scrape over the chip with the same spatula, to clear out all the paste left on the surface of the stencil.

With a clean cloth wrapped around your index finger, wipe down over the top of the stencil. This will help pack in the paste even further & clean out any debris left on top.
![Wipe the stencil down with clean cloth](images/3/37/Wipe_the_stencil_down_with_clean_cloth.png)
Now, you'll need to switch out your 2 fingers to curved tweezers
![Tweezers holding down the stencil](images/3/36/Tweezers_holding_down_the_stencil.png)
And it's time for forming the solder balls using Hot Air.

Using low heat & low airflow, like 320C / 25 air flow, heat the IC from far away, like 10inches and go in slow circles around the perimeter.
![Heating the IC](images/1/1b/Heating_the_IC.png)
Over a 45 second period, you'll want to slowly inch closer and closer to the IC.

Making sure the paste doesn't bubble over.

You'll then see the paste turn into solder balls.

Once all the solder balls are formed, you can take the heat away.

Wait about 5 seconds, allowing the solder balls to turn solid.

Then quickly pop out the IC from the stencil. Use the scalpel blade to poke it out.
![CPU reball](images/1/18/CPU_reball.png)
Visually inspect the IC and make sure all the pads have solder balls & they all look even. If not, you can just clean the stencil & IC, then place the IC under the stencil again & just reball over the existing solder balls and get a "second coating" so to speak.

While holding the IC in mid air, apply heat again & reflow the solder balls at 320C / 25 airflow without adding any flux.

Then add a thin layer of flux & reflow it one more time.

Repeat the steps for the UFS chip & reball it as well.
![A03s CPU and UFS reballed](images/6/6c/A03s_CPU_and_UFS_reballed.png)
Now it's time to install both ICs.

You'll want to dab a few tiny dots of flux across the pads on the prepped donor board.

For example:
![Small dots of flux on the CPU pads on the board](images/8/86/Small_dots_of_flux_on_the_CPU_pads_on_the_board.png)
Then place the CPU onto the board & make sure to press it down flat onto the board.

And make sure the orientation is correct. At this angle, you can see it's on the upper right corner:
![A03s CPU Orientation](images/5/58/A03s_CPU_Orientation.png)
Make sure the chip is also centered. Use the gold guides to ensure the alignment is good.

Then you want to use very low heat & airflow to install it. So use the same as you used to reball the IC: 320C and 25 airflow
![Heating the CPU to install it](images/b/bc/Heating_the_CPU_to_install_it.png)
You'll want to be patient with this. you can heat it for a long time, since it's lower heat & less chance of heat damage.

So give it at least 1 minute of heating it evenly. Make sure to circle around the whole IC and make sure to hit the center as well.

If you don't see the IC snap into place, then try adding 20C to your temps and give it another 30 seconds.

If still nothing, add another 20C.

It will eventually snap into place. You can do a tiny nudge to see if it moves. This helps determine the chip is installed.

Next, you'll repeat the same steps for the UFS & install it as well.
![CPU and UFS Installed](images/5/5d/CPU_and_UFS_Installed.png)
Do a visual inspection of the ICs and the board. Look for any bumped components, bridged lines, stray solder balls, misaligned ICs, correct orientation, etc.

If all looks good, then time to test!

Fully reassemble & plug it into charge.
![A03s charging](images/d/d5/A03s_charging.png)
If you get a charging symbol like above

USB meter charging at 5V or 9V and 1A+

Then you're probably good!

Go ahead & boot up the phone & confirm it's able to boot too!
![A03s Storage](images/3/3a/A03s_Storage_.png)
If it boots, then you're good to go!

It is recommended to run a Smart Switch Backup right away & get the data ASAP. Sometimes, these CPU Swaps can be unstable.

So don't risk it... get the data ASAP.

If the phone doesn't boot, recheck all the work you did.

Try pulling the CPU and UFS and see if anything looks funky.

Try checking UFS on a UFS programmer to see if it detects.

Check for any bumped or missing components.

Check if PC detects it in the Device Manager

If all else fails, try reballing CPU and UFS again & reinstall.

Worst case, try another donor board.

Lastly, it could just be a dead CPU or dead UFS & data is not recoverable
