# Drum trainer


## Summary

The drum trainer provides detailed information on accuracy, synchronicity and dynamics of a live drum recording.
The tool uses midi and a user-defined drum pattern (instruments and limbs) as main inputs. AI learning should enhance the tool.


## Background

A **beginner drummer myself** since a few weeks (digital Roland drumkit) I was faced from the beginning with issues related to timing accuracy and synchronisation between limbs. Also I have insufficient control over dynamics and independence (for example hitting harder on the hihat when I hit my kick at the same time).
This of course is very normal for a beginner drummer. I have no (human) teacher to give me feedback/correct me on those issues.
Basically I only have my ears (to listen to my recording) and the very simple accuracy scorer built-in into the digital drum module.
I could also have used the "piano-roll" view on a DAW (Digital Audio Workstation) to monitor the deviations between my drum hits and the metronome clicks and to measure the velocities (=dynamics).
However none of the above methods gives me a quick, "objective" insight in my issues.

In order to get a better and detailed view on my "symptoms" I **developed a simple Excel-based (vba) analyser tool**. The tool has the following features:
* **inputs**
  * metronome beats per minute
  * time signature
  * time deviation margin (for calculating scores)
  * intended drum pattern (any number of bars, for each instrument indication where left/right hand/foot is expected to hit, accented/unaccented hits) (no limitations to complexity of pattern, number of bars etc.)
  * midi commands (time, instrument, velocity), copy/pasted from a simple midi-monitor app which reads midi from USB port
* **outputs for each combination limb/instrument**
   * statistics (average time deviation, standard deviation of time deviations)
   * score (% within margin)
   * chart: time deviation vs deviation,, velocity vs time
* **general outputs**
  * chart synchronicity of simultaneous events
  * score (% synchronicity within margin)
  * midi roll (to playback, different speeds possible)
  * full analysis history

Some images from a pattern I exercised:

**Drum pattern** (defined by user)

R = right accented  L = left accented  r = right unaccented

The score is more tolerant for unaccented hits (in real music it's mostly the downbeats and accents that need to be the most accurate)

![Drum pattern](/Drum_pattern.png)

**Scores per instrument/limb** (average, standard deviation, % inside margins)

![Scores](/Scores.png)

**Time deviations per instrument/limb in centiseconds** (red lines are "margins", in this example about +-2.6cs)

The better the drummer the lower the margin should be set (for a "fair" score)

![Time deviation chart](/Time_deviation_chart.png)

**Synchronicity** in case multiple instruments were hit at same time (first hit instrument = 0)

![Synchronicity chart](/Synchronicity_chart.png)

**Play dialog** (allows to playback any combination of instruments from selected bars, can be slowed down)

![Play dialog](/Play_dialog.png)

So far the tool was **very useful in helping me to quickly observe my symptoms** (for example my right "kick" foot being too rushy). 
After observing a symptom I try to "diagnose" it and find ways to cope with it (adjusting set-up such as position/height of throne, adjusting position of devices, isolated exercises etc.)

The overall result for myself is (in my opinion) a steeper learning curve compared to not using this tool.
The **tool helps me to tackle an issue from the very beginning**. Without this tool I would learn wrong habits, which would be difficult to get rid of later.
The weak link in this issue solving chain is still the absence of a human teacher who would teach me the right way to solve an issue.
I can accept this weakness for now and find myself progressing faster with than without the tool.


## How is it used?

The tool is **intended for beginning to intermediate drummers** to get better at "live" drumming, but could also be used by professionals to detect any issues they may not be aware about.

The tool has great potential to be expanded with **AI technology**:
* providing **verbal output** to the user (feedback, recommendations, exercise suggestions) Example:
"Your right feet (bass drum) tends to kick about 100ms before you hit the snare. This causes a flamming sound.
On unaccented beats your right feet tends to kick 200ms before you intended, giving a rushy impression. Your left hand is irregular playing eights on the hihat. To obtain better accuracy, do the following exercises: ..."
* **pattern-less analysis**: the current tool requires a pattern to compare the midi input with. A more advanced version would be able to score any input by "guessing" what the user intended to play, and with which hand/foot he played it. This can be achieved by learning common patterns in the drum world, being able to figure out what would be a logical use of limbs for the pattern and learning how the specific drummer usually plays.
* **collecting information and data from different users** in order to find patterns in issues, and learn which exercises give fastest results
* **generating exercises** by extrapolating on other exercises which proved to be effective
* **examinator game** personalized set of scored exercises in correspondence with user's current level
* **metronome-less analysis**: the current tool requires the drummer to record with a fixed metronome tempo (in order to get a fixed time reference to calculated the time deviations). A more advanced version would allow to analyse the recording even if the tempo of the recording varies slightly (which would be more realistic in a live environment). This would require a feature that can determine the momentary tempo.

## Data sources 

Data source is **midi-output from a digital drumkit** (like Roland, Alesis...).

Expanded with AI (see above) extra data sources could be analysis data from different users.

## Challenges

* This tool will only be able to provide **feedback on the "symptoms"** observed (such as kicking the drum bass to early, hands being uneven etc). 
However it **will not be able to observe any of the causes underlying these symptoms** (such as position of the player, motorics of the limbs etc)
Even in my experience the volume of the metronome can affect the performance! (the louder the metronome, the better the result...)

* The **current version of the tool requires some understanding of statistics and being able to read X-Y charts**. Though basic, not every drummer will be familiar with interpreting such information or "like" this. Therefore a more "human" approach to provide feedback is required (see AI below).

* This tool is **not intended to evaluate musicality**. In real live performance human accuracy, synchronicity and dynamics "errors" may give a nice flavour to a performance, and sometimes even intended. Moreover today's DAW's (Digital Audio Workstations) can easily "humanize" or "de-humanize" (quantize) recorded input.

* The tool **will not be able to replace a human professional teacher (nor does it intend it)**. The sole purpose of the tool is to have an extra toolbox for building a solid drum technique as a foundation for good musical live performances.


## What next?

The tool is Excel-based, but is not user friendly. The input cannot be taken directly from the midi-output (needs to be copy/pasted from a midi-monitor software).
The tool shows detailed graphs and scores, but doesn't give verbal feedback to the user in a friendly way, nor does it suggest exercises.

In summary the tool could evolve into a tool that:
* reads the **input directly from the drum midi-out** (or one step further from converted drum-only **audio signal**)
* provides **verbal output** to the user (feedback, recommendations, exercise suggestions) 
* available as an app on **PC, tablet or smartphone**
* **gathers information and data from different users**
* **generates effective exercises** and personalized **exams**
