# EasyEffects_Presets
BayouGuru's EasyEffects Presets!

This repository mirrors the contents of BayouGuru's 
"/.var/app/com.github.wwmm.easyeffects/config/easyeffects/output" directory 
where EasyEffects stores its output presets data. BayouGuru makes no warranty
as to how well these presets may or may not work on your system.  As a matter
of fact, they may damage your system if used improperly!

BayouGuru is no longer using EasyEffects.  These presets
are designed to run on a large Klipsch Surround Sound System via a Yamaha
RX-A840 A/V Receiver.  The system has been set using YPAO for Natural sound.
They should sound decent-enough on any system that is sufficiently capable
of full-range frequency reproduction, i.e.:  a system with a subwoofer and/or
large speakers.  Additionally, I use the A/V Receiver's remote to control the
volume in the house, so the computer is always outputting 100% volume to the
Yamaha A/V Receiver via the HDMI connection.

These presets were NOT DESIGNED FOR USE ON LAPTOPS OR SMALL
SPEAKERS!  Having said that, the presets that filter out the bass should work
quite well on laptops.  Those presets would be the "125HP...", "TrainCams" 
and "Vocal Clarifier" presets, which BayouGuru designed for their named 
purposes. Any and all presets that use the "BE" (Bass Enhancer) can blow up 
your speakers if they are not designed to handle a lot of very low 
frequencies! How to tell if you should or should not use them? Simple! If
your audio system is capable of producing bass you can "feel" from across the
room, then you can probably use the presets with the Bass Enhancer without
too much worry as long as you pay attention to your volume, being on the
listen for any distortion of the bass, which, if heard, means you need to 
turn it down a bit before you damage your system!

# Preset List/Descriptions:

The "125HP+AG+C+Max" preset was designed for nighttime/unobtrusive TV watching,
as it filters out the bass that tends to rumble through the house.  The effects 
used are:  a 125Hz High-Pass Filter (removes bass frequencies from 125Hz downward)
-> AutoGain (maintains a minimum level) -> Compressor (keeps varying levels under 
control) -> Maximizer (boosts the overall volume like normalizing does for mp3's, 
but in near real time and, ideally, not to the point of clipping)

"AG+BE+Cry+M" is a music preset for music that could use some help on the bottom 
andtop end by using a Bass Enhancer and the Crystallizer to enhance the bass and 
high frequencies respectively, with the Maximizer being used both as a compressor 
and as a maximizer.  I do tend to tweak the settings of this preset a lot, the
specifics depending on the source music.

"AG+C+Max" is my main preset!  I use it almost all the time for everything.  It's 
an AutoGain effect feeding into a Compressor, then into the Maximizer.  This does 
a very good job of reducing the widely varying volume levels of YouTube Videos, 
Live TV, and many other different streaming services as well as the sound from a 
local record player and an mp3 collection.  

"AG+Comp+Cry+BE+Max" is another music preset, adding additional Compression to the
"AG+BE..." preset above.  Rarely used as it is still a bit of a work in progress.

"BE+Cr+Max" is yet another music preset, this one is specifically designed for use
with sources that do not have volume issues, such as the output of certain music 
players which normalize their output, like VLC, SM Player & Audacious, for example.
It adds "depth" and "sparkle" for that "live concert" kind of sound.

"C+Cry+BE+Max" is a music preset for non-normalizing players and/or more dynamic 
music content that is more in need of level/volume correction.

"Max" is simply a Maximizer to boost overall volumes.

"Monauralized and Maximized" is useful for podcasts that put their audio to one 
side or the other, whether on purpose or by accident.  It sums both channels to the
middle and maximizes the volume.  This is designed primarily for spoken word 
applications like podcasts, historical videos or audiobooks.

"TrainCams" is a unique preset for listening to live webcams of trains/train yards,
a.k. "Virtual Trainspotting". It removes both the high and low frequencies so the 
brake squeal is not so loud and it is easier to hear the engines and other things.

"Vocal Clarifier" was designed for a specific situation where the bacground music 
and noise was drowning out the voices, so this was designed to help with that.

# Installation

The easiest way to install these presets is to download them to your preferred
download directory, then use EasyEffects' "Import Preset" function to import them.

Alternatively....

You could Download and save these presets to  "/.var/app/com.github.wwmm.easyeffects/config/easyeffects/output" on your 
system (if using the EasyEffects Flatpack). 

If you are using a non-flatpack version of EasyEffects on Linux, presets are likely
stored in "~/.config/easyeffects/output".  

Once you have copied the new presets to the appropriate directory, close and restart
EasyEffects, then the new presets should be listed in your available output presets.
Enjoy!
