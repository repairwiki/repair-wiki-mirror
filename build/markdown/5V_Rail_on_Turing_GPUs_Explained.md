---
title: "5V Rail on Turing GPUs Explained"
pageid: 430
revid: 928
kind: explanatory_guide
source: "https://repair.wiki/w/5V_Rail_on_Turing_GPUs_Explained"
history: "https://repair.wiki/index.php?title=5V_Rail_on_Turing_GPUs_Explained&action=history"
permalink: "https://repair.wiki/index.php?oldid=928"
last_edited: "2023-11-07T21:55:56Z"
contributors:
  - "ASRepairs"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for RTX 2060"
  - "Explanatory guides for RTX 2070"
  - "Explanatory guides for RTX 2080"
  - "Explanatory guides for RTX 2080Ti"
infobox:
  Device: "RTX 2060, RTX 2070, RTX 2080, RTX 2080Ti"
  Type: "Circuit"
  Difficulty: "2. Medium"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# 5V Rail on Turing GPUs Explained

This page explains how the 5V rail is created and what it is used for in Nvidia Turing GPUs.

## The Controller Circuit
Turing cards usually uses [https://www.farnell.com/datasheets/3180384.pdf MP28167] or similar to step down 12V to 5V that is used to power different ICs found on Turing cards.

On lower end cards, 5V is created by a 3 legged LDO.
![5V Rail location on the board (RTX 2080 Ref) (Figure 1)](images/8/81/5v_turing_board.jpg)
![Schematic view of the 5V circuit. (Figure 2)](images/b/b8/5v_turing_schematic.jpg)
Markings on the board and schematic may differ from one GPU vendor to another, however, the circuit is almost always the same.

5V is a fairly simple rail that is usually the first to turn on. Below, (Figure 3) is the enable signal for it. The controller generates its own VCC.
![Enable signal for 5V buck converter (Figure 3)](images/3/31/5v_enable_turing.jpg)

## Usage
5V is used as VCC for other ICs on the board such as 1.8V regulator etc.

Since it is the first rail to turn on, If PGOOD signal from the controller is not generated then every other rail on the card WILL NOT turn on.

## Common Problems
Here are common problems for the 5V rail and how to fix them.

### No voltage out on the 5 V rail
First thing to check is the EN signal which should be 2+ V followed by Vin which should be 12 V (Figure 2) if one of them is missing then check the schematic and follow the signal to find the culprit, it's usually a faulty resistor.

After making sure both of the above are there, check the VCC  pin. If there is no 5 V on it then most likely the controller is faulty and needs changing.

### Short on 5V rail
The only things that can short 5V rail is either a capacitor or an IC. Simply apply Isopropyl alcohol on suspected shorted components and inject voltage on the rail to reveal the shorted component.

### No PowerGOOD signal
PG signal from the controller is the same signal that enables the 1.8 V controller, if the 5 V buck converter doesn't form that signal the rest of the card won't work. The most likely cause is the controller itself if 5V is present without a short.

### Low voltage on 5V
This usually only happens with a faulty controller or if there is a semi-short (sub 50 ohms) where a component is drawing too much current from the 5V rail above what it's rated for. Fixing this is the same as finding a short (because it most likely is).
