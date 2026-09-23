---
title: "Diagnosing HDMI Port issues using Pairs and Patterns technique"
pageid: 8798
revid: 12834
kind: explanatory_guide
source: "https://repair.wiki/w/Diagnosing_HDMI_Port_issues_using_Pairs_and_Patterns_technique"
history: "https://repair.wiki/index.php?title=Diagnosing_HDMI_Port_issues_using_Pairs_and_Patterns_technique&action=history"
permalink: "https://repair.wiki/index.php?oldid=12834"
last_edited: "2025-11-23T07:18:46Z"
contributors:
  - "VCCBoardRepairs"
  - "Ben ProFixerr"
anonymous_edits: 0
categories:
  - "Explanatory guide"
  - "Explanatory guides for PlayStation 5"
  - "Explanatory guides for PlayStation 5 Pro"
  - "Explanatory guides for PlayStation 5 Slim"
  - "Explanatory guides for Playstation 4"
  - "Explanatory guides for Playstation 4 Pro"
  - "Explanatory guides for Playstation 4 Slim"
  - "Explanatory guides for Xbox"
  - "Explanatory guides for Xbox One S"
  - "Explanatory guides for Xbox One X"
  - "Explanatory guides for Xbox Series S"
  - "Explanatory guides for Xbox Series X"
  - "Missing device page"
infobox:
  Device: "PlayStation 5, PlayStation 5 Pro, PlayStation 5 Slim, Playstation 4, Playstation 4 Pro, Playstation 4 Slim, Xbox One X, Xbox One S, Xbox Series S, Xbox Series X, Xbox"
  Type: "Troubleshooting/Diagnostics"
  Difficulty: "1. Easy"
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# Diagnosing HDMI Port issues using Pairs and Patterns technique

## 🔍 **The Basics**
The image of the t824 mechanic reader breaks down the two sections of the HDMI circuit readings:

  - Pairs (highlighted in green)**

  - Patterns (the rhythm side)**

  - Please note, *all* hdmi readings are the *same***

Meaning, that this method works for all game console hdmis.

There is one clarification with xbox series x, series s and one x they all have a diode mode reading vs OL on pin 14 on the board (pin 17 on the reader normally)![Pairs and patterns.jpg](images/9/94/Pairs_and_patterns.jpg)

Xbox Series X will however show OL when the top board is not connected but the diode mode will populate once the board is attached.
## ✅ **Identifying the Pairs**
### **What are the pairs?**
The pairs are groups of two identical diode readings, always separated by a ground reading.

### **How to find them:**
Orientation matters: Depending on how the reader is plugged in, the pairs can start in the bottom right corner.

### **Diode Mode Readings:**
A diode reading measures voltage drop between two points.

The multimeter sends voltage from one probe through the board’s components, and when it reaches the other probe, it displays the voltage drop.

#### **Example:**
![Green highlighted are pairs and pink highlighted is the patterns side. The color overlay shows the trace path for each line.](images/c/c3/Hdmi_pairs_and_patterns.png)Top left reading: 0.85

We call this a .85 diode mode reading (it’s actually 0.85 volts).

### **How to identify pairs:**
![Hdmi pairs.png](images/a/a8/Hdmi_pairs.png)
Start by looking for identical readings.

#### **Example:**
0.85 → 0.07 (ground) → 0.85

These two .85 readings are a pair, with ground in between (like an Oreo cookie).

### **What to expect:**
There are 4 identical pairs (8 separate readings), each with a ground in between.

Readings should be identical, with an acceptable variance of ±0.01.

#### **Example:**
If the reading is 0.85, acceptable variance is 0.84 or 0.86.

Once you confirm all 4 pairs are OK, move to the Patterns.

## 🎵 **Understanding the Patterns**
### **Why are they called Patterns?**
Unlike the pairs, these readings aren’t uniform — they follow a rhythm pattern.

### **How to check Patterns:**
![Hdmi patterns.png](images/1/16/Hdmi_patterns.png)
We use a simple song/rhythm to remember the expected readings:

Start at the end of the line (22 in this case) and work backward.

### **What you’re looking for:**
Readings in the range of .500, .600, .700

The readings do not need to be identical, just within range.

#### **Example:**
Reading 22 = 0.70 → OK (in range)

Reading 21 = 0.56 → OK (in range)

As long as they fall within the .500 - .700 range, they’re considered good.

## 🔥 **Why This Method Matters**
This method is unique , it’s something I developed specifically for HDMI circuit testing.

### **Pro Tip:**
When verifying the circuit:

Start at one end for the pairs

Start at the other end for the patterns

This prevents misreads and confusion.

## ⚙️ **Quick Circuit Overview**
### **Pairs Side:**
Goes directly to the encoder/retimer with only filters or bidirectional diodes.

➤ This side produces the image.

### **Patterns Side:**
Goes to a handoff IC (Xbox) or diodes/resistors (PlayStation) before going to the encoder/retimer.

➤ This side negotiates image quality, frame rate, etc.

There is a range of readings that can be displayed on the Mechanic Reader and a Multimeter when measuring diode mode.

The range looks like this generally:

GROUND 0.00 … 0.100 … 0.200 … 0.300 … 0.400 … 0.500 … 0.600 … 0.700 … 0.800 … 0.900 … 1.000 OL

Anything generally in the .00-.300 and the .900-1.00  zone is considered ‘bad’. This isnt always the case, but its often the case.
