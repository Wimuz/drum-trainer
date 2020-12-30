# Project Title

Drums trainer

## Summary

The drum trainer provides advice to the aspiring (beginner or intermediate) drummer based on analysis of a recording.
The tool records midi or audio, figures out which drum pattern the drum player intended to play, analyses the accuracy and synchronicity of the recorded pattern, 
provides feedback to the player and suggests exercises to help solve any issues.
For example: "Your right feet (bass drum) tends to kick about 100ms before you hit the snare. This causes a flamming sound.
On unaccented beats your right feet tends to kick 200ms before you intended. To get better accuracy, do the following exercises: ..."


## Background

A beginner drummer myself since a few weeks (digital Roland drumkit) I was confronted from the beginning with issues related to timing accuracy and synchronisation between limbs.
This of course is very normal for a beginner drummer. I have no (human) teacher to give me feedback/correct me on those issues.
Basically I only have my ears (to listen to my recording) and the very simple accuracy scorer built-in into the digital drum module.
I could also have used the "piano-roll" view on a DAW (Digital Audio Workstation) to monitor the deviations between my drum hits and the metronome clicks.
However none of the above methods gives me a quick insight in my issues.

In order to get a better and detailed view on my "symptoms" I developed a simple Excel-based (vba) analyser tool. It shows me graphically, statistically and with % scores where my main issues are located by comparing with a pre-set pattern.
For example a chart with on the X-axis the time and on the Y-axis deviations (vs metronome) per instrument/hand .

So far the tool was very helpful in helping me to quickly observe my symptoms (for example my right "kick" foot being too rushy). 
After observing a symptom I try to "diagnose" it and find ways to cope with it (adjusting set-up such as position/height of throne, adjusting position of devices, isolated exercises etc.)
The overall result for myself is (in my opinion) a steeper learning curve compared to not having such a tool.
The tool helps me to tackle an issue from the start. Without this tool I would learn wrong habits, which would be difficult to get rid of later.
The weak link in this issue solving chain is still the absence of a human teacher who would teach me the right way to solve an issue.
I can accept this weakness for now and find myself progressing faster with than without the tool.


## How is it used?

The tool is intended for beginning to intermediate drummers, but could also be used by professionals to detect any issues they may not be aware about.


## Data sources and AI methods

Data source is midi-output from a digital drumkit (like Roland, Alesis...).
With addition of an add-on that converts audio into midi-like commands the tool could also be used with acoustical drums.

## Challenges

This tool will only be able to provide feedback on the "symptoms" observed (such as kicking the drum bass to early). 
However it will not be able to observe any of the causes (such as position of the player, motorics of the limbs etc)

## What next?

The tool is Excel-based, but is not user friendly. The input cannot be taken directly from the midi-output (needs to be copy/pasted from a midi-monitor software).
The tool shows detailed graphs and scores, but doesn't give verbal feedback to the user in a friendly way, nor does it suggest exercises.

In summary the tool could evolve into a tool that:
- reads the input directly from the drum midi-out (or one step further from converted drum-only audio signal)
- provides verbal output to the user (feedback, exercise suggestions)
- available as an app on PC, tablet or smartphone
- gathers information from different users, finds patterns in issues, learns which exercises give fastest results