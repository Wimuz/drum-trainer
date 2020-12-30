# Drum trainer


## Summary

The drum trainer provides technical advice to the aspiring drummer based on analysis of a recording.
Using midi or audio as input the tool analyses the accuracy, synchronicity and dynamics of the recording and provides recommendations.


## Background

A **beginner drummer myself** since a few weeks (digital Roland drumkit) I was confronted from the beginning with issues related to timing accuracy and synchronisation between limbs. Also I have insufficient control over dynamics and independance (for example hitting harder on the hihat when I hit my kick at the same time).
This of course is very normal for a beginner drummer. I have no (human) teacher to give me feedback/correct me on those issues.
Basically I only have my ears (to listen to my recording) and the very simple accuracy scorer built-in into the digital drum module.
I could also have used the "piano-roll" view on a DAW (Digital Audio Workstation) to monitor the deviations between my drum hits and the metronome clicks and velocities.
However none of the above methods gives me a quick, "objective" insight in my issues.

In order to get a better and detailed view on my "symptoms" I **developed a simple Excel-based (vba) analyser tool**. The tool has the following features:
* **inputs**
  * metronome beats per minute
  * time signature
  * time deviation margin (for calculating scores)
  * intended drum pattern (any number of bars, for each instrument indication where left/right hand/foot is expected to hit) (no limitations to complexity of pattern)
  * midi commands (time, instrument, velocity), copy/pasted from a simple midi-monitor app which reads midi from USB port
* **outputs for each combination limb/instrument**
   * statistics (average time deviation, standard deviation of time deviations)
   * score (% within margin)
   * chart: time deviation vs deviation,, velocity vs time (for each combination limb/instrument)
* **general outputs**
  * chart synchronicity of simultaneous events
  * score (% synchronicity within margin)
  * midi roll (to playback, different speeds possible)

So far the tool was **very helpful in helping me to quickly observe my symptoms** (for example my right "kick" foot being too rushy). 
After observing a symptom I try to "diagnose" it and find ways to cope with it (adjusting set-up such as position/height of throne, adjusting position of devices, isolated exercises etc.)
The overall result for myself is (in my opinion) a steeper learning curve compared to not having such a tool.
The **tool helps me to tackle an issue from the start**. Without this tool I would learn wrong habits, which would be difficult to get rid of later.
The weak link in this issue solving chain is still the absence of a human teacher who would teach me the right way to solve an issue.
I can accept this weakness for now and find myself progressing faster with than without the tool.


## How is it used?

The tool is **intended for beginning to intermediate drummers** to get better at "live" drumming, but could also be used by professionals to detect any issues they may not be aware about.

The tool gives feedback and recommendations such as:
For example: "Your right feet (bass drum) tends to kick about 100ms before you hit the snare. This causes a flamming sound.
On unaccented beats your right feet tends to kick 200ms before you intended, giving a rushy impression. Your left hand is irregular playing eights on the hihat. To obrain better accuracy, do the following exercises: ..."


## Data sources and AI methods

Data source is **midi-output from a digital drumkit** (like Roland, Alesis...).
With addition of an add-on that converts audio into midi-like commands the tool could also be used with acoustical drums.

## Challenges

This tool will only be able to provide feedback on the "symptoms" observed (such as kicking the drum bass to early). 
However it will not be able to observe any of the causes (such as position of the player, motorics of the limbs etc)

This tool is not intended to evaluate musicality. In real live performance human accuracy, synchronicity and dynamics "errors" may give a nice flavour to a performance, and sometimes even intended. Moreover today's DAW's (Digital Audio Workstations) can easily "humanize" or "de-humanize" (quantize) recorded input.

Nor does the tool intend to replace a human professional teacher. 

The sole purpose of the tool is to assist partly in building a solid drum technique as a foundation for good musical live performances.


## What next?

The tool is Excel-based, but is not user friendly. The input cannot be taken directly from the midi-output (needs to be copy/pasted from a midi-monitor software).
The tool shows detailed graphs and scores, but doesn't give verbal feedback to the user in a friendly way, nor does it suggest exercises.

In summary the tool could evolve into a tool that:
- reads the **input directly from the drum midi-out** (or one step further from converted drum-only **audio signal**)
- provides **verbal output** to the user (feedback, recommendations, exercise suggestions)
- available as an app on **PC, tablet or smartphone**
- **gathers information and data from different users**, finds patterns in issues, learns which exercises give fastest results
