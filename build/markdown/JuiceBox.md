---
title: "JuiceBox"
pageid: 2436
revid: 5881
kind: other
source: "https://repair.wiki/w/JuiceBox"
history: "https://repair.wiki/index.php?title=JuiceBox&action=history"
permalink: "https://repair.wiki/index.php?oldid=5881"
last_edited: "2025-03-14T16:28:20Z"
contributors:
  - "ChrisC"
  - "Jeremy.niles"
anonymous_edits: 0
categories:
infobox:
licence: "CC BY-SA 3.0, https://creativecommons.org/licenses/by-sa/3.0/"
snapshot: "2026-09-23"
generated: true
---

# JuiceBox

([up to EV chargers section](EV_chargers.md))

NOTE: This page was created in early October, in the wake of the Enel X shutdown, to start to capture JuiceBox information.  If you spot some incorrect or missing information below, FIX IT YOURSELF!  This is a wiki, meaning it's editable by anyone -- create an account and edit in the correction.  See the main "EV chargers" page above for more information about this site.

## Manufacturer / model introduction
The JuiceBox series of EVSE hardware was first developed by eMotorWerks (EMW), an independent EV shop founded by Val Miftakhov, and they brought the first generation JuiceBox to market in 2013.  In 2017 the company was purchased by the Italian utility company Enel, operating under the subsidiary EnerNOC, which was later rebranded as Enel X and Enel X Way.  In 2024, Enel suddenly shut down their North American operations.

JuiceBox hardware models:

- original JuiceBox, funded via [https://www.kickstarter.com/projects/emw/emw-juicebox-an-open-source-level-2-ev-charging-st Kickstarter campaign] in 2013; "Base" model was simple metal box; "Premium" model base was designed to look like a huge AA battery; both were available as rewards to campaign backers in either assembled form or kit form (cheaper)
- JuiceBox Classic 40 (basic 40 Amp EVSE, no connectivity / app), released 2013
- JuiceBox Pro 40 (advanced 40 Amp EVSE with connectivity / app), released 2013
- JuiceBox Pro 40 (no model name difference?), overhauled under Enel X, released in 2017
- also 32 Amp, 48A and 75A versions of the above
- JuiceBox Pro 40 Lite (same but stripped of some features)
- JuiceBox 2.00 hardware
- JuiceBox 2.01 hardware
- smartphone app Enel X Way ([https://apps.apple.com/us/app/enel-x-way/id1377291789 Apple]/[https://play.google.com/store/apps/details?id=com.enel.mobile.recharge2&hl=en_US Android]), required to make configuration changes to the stations (via Enel X cloud), for example changing the current / amperage setting
- smartphone app JuiceNet, predecessor to above that was produced by EMW, deprecated in March 2024
- JuiceRouter, a LTE-to-Wifi gateway used to connect up to 16 stations to the cloud

## Reference information from manufacturer, both marketing and technical
WARNING: in Oct 2024, Enel X suddenly announced that it was shutting down, and many of these resources may not be available. (check archive.org)

## Oct 2024: Enel X shutdown and the race to support those abandoned customers
- Enel X shutdown news: [https://www.theverge.com/2024/10/2/24260316/juicebox-ev-chargers-enel-x-way-closing-discontinued-app The Verge], [https://electrek.co/2024/10/02/enel-x-way-north-america-is-shutting-down-heres-what-we-know/ Electrek]
- [https://www.juiceboxnorthamerica.com/ Enel X "creditor claims information" website]
- [https://chargelab.co/blog/enel-x-way-migration ChargeLab: blog post saying they will support orphaned JuiceBox *commercial* charging hardware]
- [https://www.linkedin.com/feed/update/urn:li:activity:7248055883501297664/ ChargeLab: LinkedIn post from CEO Zak LeFevre providing more details], including an Oct 11th deadline after which it might be impossible to migrate
- Liberty Plugins: [https://www.libertyplugins.com/blog/three-options-for-juicebox-users-after-enel-x-way-shutdown/ Blog post on available options for commercial accounts affected by Enel X Way market exit]
- [https://chargelab.co/blog/migration-update ChargeLab: Nov 2024 update on how they rescued 1400+ Enel X chargers]
- [https://ampup.io/blog/ampup-can-keep-your-enel-x-way-commercial-ev-chargers-powered-up-and-online AmpUp: blog post saying they can take over Enel X's commercial EV hardware]
- [https://www.noodoe.com/solutions/enel-x-way-migration-solutions Noodoe: website section saying they can take over Enel X's commercial EV hardware] (now forwards to article below)
- [https://www.noodoe.com/blog/keep-your-enel-x-juicebox-chargers-online-with-noodoe-ev-os Noodoe: Dec 2024 blog article walking through the issues and solutions]
- [https://pulseenergy.io/blog/reprogramming-an-enel-x-juicebox-40-charger-to-pulse-energy PulseEnergy: offering same, with specific instructions on how to point the station to them]
- [https://epiccharging.com/enelx-chargers-transfer EpicCharging: offering same]
- but also note that many in the business think this ultimately won't work and that you need to start over with new hardware: [https://www.linkedin.com/feed/update/urn:li:activity:7248001945766883329/ LinkedIn post from Sona VP], [https://www.linkedin.com/posts/abasselhage_seeing-a-lot-of-posts-by-ev-charging-software-activity-7248178005456379904-al14/ LinkedIn post from Red-E CEO]
- [https://teslamotorsclub.com/tmc/threads/juicebox-enel-x-way-north-america-is-shutting-down-oct-11-2024.334733/ TMC thread on shutdown and support options]
- [https://juice-rescue.org/ JuiceRescue]: a DIY community website set up in the shutdown aftermath; includes the [https://github.com/JuiceRescue/juicepassproxy juicepassproxy project on GitHub] to implement the protocol on open source
- The [https://www.openevse.com/ OpenEVSE] community is working on a solution that would tap into the existing hardware to provide basic remote monitoring functions, and maybe control; see the [https://openev.freshdesk.com/support/discussions OpenEVSE support forums], including
  - thread: [https://openev.freshdesk.com/support/discussions/topics/6000070042 JuiceBox / ENEL X Shutting Down] (includes hardware details and interface ideas for replacement control board)
  - thread: [https://openev.freshdesk.com/support/discussions/topics/6000069506 question about clamps and LEDs] (hardware details on current clamps and indicator LEDs)
  - thread: [https://openev.freshdesk.com/support/discussions/topics/6000070043 Hardware retro-fit with OpenEVSE] (JuiceBox hardware details including many photos of internal components)

### Immediate actions for JuiceBox owners to take before Oct 11th, that can only be done via app:
- Note that this might be as early as 12:01am Oct 11th CEST (European time), since Enel is headquartered in Italy; in the USA that would be Thursday Oct 10th at 3:01pm PT / 6:01pm ET.
- Thanks up front to Kishore Devisetti and the Noodoe team ( [https://www.linkedin.com/feed/update/urn:li:activity:7249589725525610496/ LinkedIn post 1] , [https://www.linkedin.com/posts/kishoredevisetti_ev-chargers-activity-7249967662372392961-gOOG LinkedIn post 2] ) for much of the following details.
- Home --> Settings --> Configuration --> Plug & Charge
- Home --> Settings --> Configuration --> Default Power --> Max power
- Note on the config above:  Make any desired changes to max charge amps. Double check that your station is set to match your breaker; for example, a station on a 40 Amp breaker should be set to deliver no more than 32 Amps (due to the 80% rule for continuous loads). It could have been set wrong the whole time and still be working, but only because you had an EV that pulled a lower current. If you get a new EV it could lead to blown circuit. Just double check it while you still can.
- Home --> Settings --> Smart Charging --> Scheduled charging --> Disabled
- Note on the config above: If Smart Charging is enabled, your JuiceBox will only charge cars during a preset time window. Once the cloud/app is discontinued, we do not know if this setting will become permanent, and we don't know how it will behave during the DST changes twice a year. Most EVs have TOU / time window capability built in, and can be set the car's UI or in the car's app (or both).
- History --> Select the time period --> Take Screenshots of history if needed
- My Account --> Wallet --> Payment methods --> Delete any current credit cards
- Consider disabling any charge energy limits.
- After making last change, edit OCPP server setting to null?

## Operational / fault indicators
e.g. LED blink patterns

## Common failure modes
e.g. parts that are known to break pretty easily

## How to disassemble
especially if special tools or sequence is required

## Common parts that need replacement
procedures for doing that work

sources / alternates for those parts

## how to update firmware
hardware required, e.g special cable

software tools required

firmware sources (mfg, third party, DIY)

description of port location

description of software steps

## links to forum threads where repair of this hardware is described
- link
- link

## links to videos (e.g. Youtube) where repair of this hardware is described
- link
- link
