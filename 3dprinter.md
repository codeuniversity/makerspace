[Main](README.md) | [Access](access.md) | [Equipment List](equipment.md) | 
------------------------
[Makerspace website](https://codeuniversity.github.io/makerspace/) |
[Makerspace github repo](https://github.com/codeuniversity/makerspace/) | [Makerspace Slack channel](https://codeuniversity.slack.com/archives/C011CN2SMFY)

------------------------

# Prusa i3 MK3 3D printer

The MakerSpace currently has a Prusa i3 MK3 3D printer.

You can find material on the Prusa Website [https://help.prusa3d.com/tag/mk3](https://help.prusa3d.com/tag/mk3)

Please download and read the Prusa introduction manual for safe and reliable printer operation 
 [https://help.prusa3d.com/downloads/mk3/handbook](https://help.prusa3d.com/downloads/mk3/handbook)

*adapted from Prusa forum induction*

The PRUSA i3 MK3 is a very nice machine, and you will find that it is a reliable machine with great print quality. There are thousands of users who use this machine as a workhorse, and you can too.

That said, there is a learning curve and people make mistakes. If you are expecting this to be as easy as an inkjet or laser printer, it is not, but it can become that routine once you get over the learning curve.

This is a collection things most discussed on this forum as a reference for someone having problems starting (initial section) or trouble shooting (second section). None of this is “mine” but rather a collection of the advice, solutions and problems that are frequently discussed on this forum. This should be a good place to start looking for your answers. I am in no way affiliated with PRUSA, just a user who climbed this learning curve with the help of many wonderful forum members.

These hints/step are not to be used instead of thinking. Think about the problem/steps and make sure they make sense to you. This collection is provided in good faith, but you are responsible for your machine. Electricity and heat can hurt you or the machine. Make sure you are comfortable with the steps and your knowledge before jumping in.

 Please watch the introduction video here 
 [https://youtu.be/JqH41K2vq0g?feature=shared](https://youtu.be/JqH41K2vq0g?feature=shared)


![overview of Prusa 3d Printer](prusa3dprinter.png
) 
## Trouble Shooting

### General advice.
1. The first layer is ALL important. Get it right first. See steps listed above. This will prevent a lot of frustration.
2. Print something from the SD card that came with the printer. If it prints fine, and things you slice don’t then you have a slicer issue. If they don’t you have a hardware issue.
3. Determine if the issue is persistent or intermittent. Try to localize the conditions that cause it. This is the fastest way to get to an answer.
4. Start simple before getting advanced. This is true for material choice, model choice, adding the MMU upgrade.

Print comes loose from the bed during print, causing either spaghetti or a plastic tumor to grow on your extruder.
**Common causes:**
1. Poor Z Height setting (see above).
2. Print bed is not clean (see above).
3. Extruder cable knocked the print off the bed (see above).
4. Model has small footprint on the bed. Add BRIM in your slicer if the model has a flat bottom, and/or a RAFT if it has a curved bottom.
5. A part of the print has “curled” up and caught on the nozzle or PINDA sensor. Look at supports in the slicer, increase bed temperature, use an enclosure to keep the part warmer and reduce drafts.

Extruder stops extruding filament. (Works for a while then stops)
**Common causes:**
1. Tension on the extruder springs is set wrong (see above).
2. Filament spool is not free to turn creating intermittent friction or binding. (Or filament is not wound well on the roll). Fix filament holder. Consider alternate designs on Thingiverse.
3. The extruder “Hobb-Goblin” pulley is dirty and debris is following the filament into the extruder.
4. The extruder “Hobb-Goblin” pulley is warn and is no longer grabbing the filament.
5. The extruder cooling fan (that cools the heat-break) is not keeping the heat-break below the filament melting temperature so it is melting and causing a clog. If in an enclosure, open the door. Verify the fan is running.
6. Intermittent (or broken) connection in the cable bundle for the extruder stepper (not stepping), cooling fan (not cool enough) or thermistor (causing the printer to think the temperature is cooler than it is, causing it to increase temperature beyond the range of the filament). Intermittent comes and goes as the cable flexes at different Z values.
7. Bad temperature for the filament.
8. Set screw on the extruder “Hobb-Goblin” pulley has come loose allowing the pulley to spin independently of the extruder stepper motor.
9. Set screw on the extruder thermistor is loose, creating a poor temperature reading of the heat block (see 6).
10. Poor quality on the filament diameter. Measure it with a caliper over a short span. Try a different spool.

Bad surface quality on the final prints.
**Common causes:**
1. Temperature swings. Do the two PID calibrations in the menu. (See above). (Some disagree.)
2. Loose belts (see above).
3. Linear axis (X and Y) bearings are binding or jerky (technical term). Check assembly, consider lubricant.
4. Wobbly Z axis or wobbly extruder casing.
5. Belts are rubbing on the pulley. This creates a periodic “bump” that takes the shape of vertical lines on the print.
6. Slicer settings. (A topic unto itself). Try different temperatures, retraction, cooling fan, etc.
7. Poor quality on the filament diameter. Measure it with a caliper over a short span. Try a different spool.

Print suddenly shifts in X or Y and keeps printing.
**Common causes:**
1. Loose belts. (see above).
2. Extruder cable hit the print. (see above).
3. Stepper motor not secured properly.
4. Curled print hits the nozzle or PINDA sensor.
5. Bad wiring to steppers, or steppers overheating (rare), or power issues (use an UPS).
6. Binding on the axis - bearings non clean/parallel, failing or not secured properly (zip tie) to the carriage.
7. Cat, kid, or ghost bumped the extruder while printing. Punish offending party.

Heated bed struggles to keep up with hotter bed temperatures.
1. There is a potentiometer on the power supply. It comes set around 11.5V. People have reported success with increasing that to 12V to 12.5V. There is some controversy to this, read the forum for details.

## Software

There are 1000’s of free and pay tools out there for creating your models, slicing them, and so forth. This is really not the forum for that detailed a discussion, but here are some common ones so you can research them yourself.

### Slicers 
* Convert .stl files (models) into .gcode commands for your printer. These can make a HUGE difference in your print quality. Most have 100s of settings and thus a learning curve, but the knowledge of the control is worth it. 
* Common ones are: [Slic3r (use Prusa one)](https://www.prusa3d.com/page/prusaslicer_424/), KISS, Cura, Simplify3D (S3D) [Guide to slic3r]( http://www.instructables.com/id/Guide-to-Slic3r/)
* There are many Prusa Slicer introduction videos - here is a reasonable one [https://www.youtube.com/watch?v=_kIqMPNQNSw](https://www.youtube.com/watch?v=_kIqMPNQNSw)

### CAD
 * [OpenSCAD](https://openscad.org/) is opensource, powerful but complex - good if you have a programming background (even just a bit). [TinkerCAD](https://www.tinkercad.com/) is a super easy introduction to making 3d Models for printing. There is also software such as [SolidWorks](https://www.solidworks.com/) and also [SketchUp](https://www.sketchup.com/en)
* Autodesk Fusion360. Industrial level 3D modelling tool with free ascess for educational use [Fusion360 download](https://www.autodesk.com/products/fusion-360/choose-usage)
  * this intro to Fusion360 from formlabs is a good quick overview [https://formlabs.com/eu/blog/fusion-360-tutorial-basics-and-tips-for-3d-printing/](https://formlabs.com/eu/blog/fusion-360-tutorial-basics-and-tips-for-3d-printing/)
   
### Sculpting type modeling
* [Blender](https://www.blender.org/) and similar.

### Model and mesh Manipulation: 
* [Meshmixer](https://meshmixer.com/)
* [meshlab](https://www.meshlab.net)


 ![CODE logo](Word_AppliedSciences_Black-sml.png)
