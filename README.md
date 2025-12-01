*Better audio on Linux...A myriad of solutions!  

One of the many benefits of being a Linux user is that we have so much more flexibility in the configuration of our computing experiences versus other Operating Systems. One of those areas of flexibility is the audio subsystem. With the advent of Pipewire, Linux audio has become easier and more user-friendly than ever before. This power is coming in handy as we transition into a streaming-based entertainment model. Something that is not so user-friendly about this trend is the widely varying audio levels and quality between the different videos, songs, services, etc. For the HTPC user, this can become a significant issue, greatly affecting one's enjoyment of the Linux multimedia experience. In my HTPC environment where an A/V receiver is amplifying the sound to the speakers and sending the video to the television or monitor, I prefer to keep the computer's output volume set @ 100% output (where the signal to noise ratio is the highest), and use the A/V receiver's remote to control the volume.  

In order to keep the volume consistent between the various audio sources, there are now a number of solutions available that can greatly enhance the listening experience. What we're talking about here is real-time audio processing of the computer's audio output, be it analog or digital! There are quite a few choices available to the Linux HTPC'er, each with its own strengths and weaknesses and I will address a few of those in due course here, but know that what may be better for me in my use-case may not be what is best for you in yours. That is just fine! There is very little chance of you doing any real harm to anything other than your speakers themselves by trying any or all of the listed options I am outlining below in order to see what works best for you in your particular situation. I am only presenting to you what I consider to be your best options at the time of this writing and share my experiences in trying them myself, hopefully helping you to avoid the issues that I have had to overcome in order to achieve a high degree of satisfaction with the audio output of my Linux computer.  

The scope of this list is in the improvement of the audio output from media players and web browsers while playing music or watching tv/videos, whether online or offline. For the purpose of this article, we are not concerning ourselves with microphones (aka: locally-produced audio inputs), though most if not all of the options listed do offer processing of those signals as well. I run my system in Stereo, not surround (5.1) mode, even though I am running a 5.1 surround system speaker setup with large left & right speakers (Klipsch RF-83's), a small center channel (RC-52) and surrounds (RB-51's) together with an R-100SW 10" subwoofer receiving everything below 84Hz from my Yamaha RX-A840BL. It all just sounds better with everything playing in stereo, and besides that, my music (36,000+ songs) is all recorded in stereo, most streaming TV is in stereo and most-importantly, there are no free surround sound effects that can do what these stereo effects like LUveler can do that I have been able to find despite years of searching. Frankly, I do not miss surround sound, as I run my A/V receiver in "7 channel Stereo" mode anyway. Okay, enough of that, on to the various options for audio improvement on the Linux desktop!  

**[EasyEffects](https://github.com/wwmm/easyeffects)** - Just as the name implies, this is likely the easiest way to improve your computer's audio. You can download presets for various tasks and it has an AutoGain plugin that works well to correct widely varying volumes. There is ample help documentation and the software is available in a number of packaging formats. I used this software for more than a year, and have created a number of presets for it which are available for download here on my GitHub page. I recommend EasyEffects as a good starting point for anyone who is not experienced in audio production and/or Linux and audio in general. It really is a great software package that benefits from frequent updates!  

**[JamesDSP](https://github.com/Audio4Linux/JDSP4Linux)** - This audio processing suite has an interface that is somewhat more simplified than EasyEffects, and does pretty much the same things, though I did not find the volume leveling effective enough, and the interface is not to my personal liking, but that is a personal thing particular to me and not in any way a knock against the software, as it does what it is supposed to do very well and is a great alternative to EasyEffects.  

**Calf Plugins + qpwgraph** - [Calf](http://calf-studio-gear.org/),  [qpwgraph](https://github.com/rncbc/qpwgraph) - Qpwgraph is a must-have for routing the audio in pipewire/Linux for this setup. It makes everything simpler and persistent across a reboot. Unfortunately, the Calf plugin pack does not feature an autogain type of plugin, so I used the Multiband Limiter to achieve the same effect, but this approach came with certain limitations, such as still having to go into the limiter and adjust input gains for sources that differed significantly in their recorded levels in order to achieve adequate volume without suffering a degeneration in the mix or the quality of the audio. Making this work used a lot of the knowledge gained from over 30 years of live audio production experience and I would not recommend it for this specific purpose for anyone except those really wishing to learn about how compression and gain structures really work in the digital realm. Pretty heady audio tech stuff, frankly and is very much more 'involved' to get right than the average person who is not an audio or tech nerd is going to be willing to deal with. Running the Calf plugin pack independently lets you set presets per-effect, but uses more CPU and limits the effects available to those in the Calf Plugin Pack. Not a bad solution, just not ideal for HTPC audio processing purposes.  

**Carla + LUveler Plugin + Calf plugins + qpwgraoh** - [Carla](https://kx.studio/Applications:Carla),  [LUveler](https://luveler.blogspot.com/), [Calf](http://calf-studio-gear.org/) [qpwgraph](https://github.com/rncbc/qpwgraph) - This, to me, has become the ideal full-time audio subsystem configuration for real-time audio processing on Linux, and the one I would most-recommend if you want something more powerful and flexible than EasyEffects or JamesDSP.  

LUveler is a Stereo volume leveler plugin that does exactly as the name implies. When properly configured, you can send audio into the plugin at widely varying volumes and it will all come out at very close to the same perceived volume, and it does it without distorting or affecting the sound quality, nor does it affect the bass/mid/treble ratios of the mix! Incredible! It does not have a fancy interface or anything, you simply edit the settings from the Effects Rack in Carla, which is the host for the LUveler plugin (and any others you wish to use). I cannot recommend LUveler strongly-enough! It is damn near like having a sound man/person/tech in a plugin and is the main plugin that I would run even if running no others! Wild changes in volume from video to video and source to source are a thing of the past for me! Installing the plugin on Linux is as simple as downloading the archive and extracting it to the .ladspa directory inside your home directory. Verify that Carla's plugins location settings are looking there, refresh the plugin cache in the plugin list, then you can add the plugin into Carla's rack. Patch Carla into the signal path in the Patchbay (it usually does this itself automatically), click save in Carla so your settings will be saved.  

Running the Calf plugins from within Carla instead of running them directly lowers the overall CPU usage versus the qpwgraph & Calf method previously outlined and puts more and more useful potential effects all in one place for MUCH easier audio routing and processing. Carla also gives one the ability to load most any plugin format one could want to run, be it VST, LADSPA, LV2 etc.  

I have added a filter, an EQ and a Bass Enhancer to Carla's rack of effects for my use case. I use the Calf Filter plugin in HighPass mode in order to remove the bass from the audio for listening when others in the house are trying to sleep, and it also works very well to remove the wind noise/rumble from train/aviation/outdoor videos. I simply bypass it when it's not needed (right click on the effect in the Carla rack, then click bypass). My Filter settings are as follows:
- Input and Output Gains - 0 db
- Resonance - -3 db
- Frequency - 142 Hz
- Slope - 36 db/octave
- Inertia - 11 ms  

I use the Calf EQ plugin to customize the audio to be more pleasing to my older ears. I also use the Calf Bass Enhancer plugin to deepen the bass in my music when jamming. This effect reminds me of the Peavey Kosmos (& Kosmos Pro) or BBE's Bass Enhancer effects that were once used on larger PA systems to make that bass you 'feel' more than 'hear', which I am a big fan of. :)  

There are multiple ways to run Carla and the associated plugins (see Carla>Configure Carla>Engine). I prefer to use it in "Continuous Rack" mode for simplicity's sake. This means the audio flows through the rack logically from top to bottom, so arranging your effects properly is very important for optimal functionality. I recommend organizing your plugins/effects as follows:
1. Filter
2. ... All effects other than LUveler (such as the Bass Enhancer & EQ)...
3. LUveler  

The reason for the Filter being first is that there is no practical sense in rendering any other effects on frequencies you are just going to remove with the filter anyway. This allows the subsequent effects to do their work on the audio you are wanting to hear instead of wasting time, CPU and bandwidth processing bass that is going nowhere when the filter is on. Doing this also means that you do not necessarily have to bypass the Bass Enhancer when watching TV with the Filter on, as there is virtually no bass there to enhance, so you generally get no or little noticeable change in sound when bypassing it.  

Your Carla Rack should always have the LUveler plugin at the bottom of the effects list as the last stop for audio before leaving the computer. Once properly configured, you can enjoy steady volumes across all media sources without much effort at all! My LUveler settings are as follows:
- Target Level - -10.0 LUFS
- True Peak - 0.0 dBTP
- Max Gain - 30.0 db
- Freeze Level - -36 LUFS
- Input Level - -0.0 LUFS
- Correction High - 100.0%
- Correction Low - 100.0%
- Corr Mix Mode - 3  

I moved Carla to Virtual Desktop 4. I leave it minimized there and hardly think about it except for when I want to either engage or disengage the filter.  

Any time you start a game or application and there is no audio output, or the audio seems excessively low in volume, you simply Alt-Tab (task switch) over to qpwgraph, patch the audio source to Carla's inputs, click save, then Alt-Tab back to your game or app and enjoy steadier audio levels, processed to your liking! Do not forget to save your settings in Carla as well each time you patch a new audio player or source/program into Carla's input so that it will also automatically reconnect the source back to its input the next time!   This will also have the knock-on effect of making the transition back to a setup that does not require qpwgraph seamless once I can figure out why Carla stopped managing the connections after a reboot.  With my rack and audio routing saved in Carla, I have also set an autorun entry in my startup folder to load Carla with my preferred initial settings after each reboot. By doing those things, the connecting and processing of the various audio sources I listen to has now become almost completely automatic and invisible, and I am no longer frequently reaching for the A/V receiver's remote to adjust the volume!  

I am using qpwgraph to maintain the persistence of the connections until I can figure out why Carla stopped doing it itself after a reboot.  Once I figure this out, that information on how to makr that happen reliably will replace this paragraph.  

# EasyEffects_Presets
BayouGuru's EasyEffects Presets!

This repository also mirrors the contents of BayouGuru's 
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
