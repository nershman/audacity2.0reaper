Audacity to Reaper project converter
=====================================

This is an experimental converter which reads Audacity project files (`.aup`), and converts them to Reaper project files (`.rpp`). Audio data saved by Audacity (ProjectName_data containing `.au` files) is also included in this process, and gets converted to `.wav`.

![screenshot](https://user-images.githubusercontent.com/1311555/44623740-b77dbb80-a8ce-11e8-8c68-a870524f1116.png)

It uses Python 3.6 and has no external dependencies.


Why
----
With this you can easily convert your old audacity projects to reaper projects if you've made the switch. You can also use it to accomodate workflows which involve preliminary recording/experimentation in Audacity and more serious mixing in Reaper.

What is preserved?
---------
Basically anything that you can do in an audacity project, can be ported to a Reaper project.
* track order
* audio locations
* track color codes
* panning
* mute/solo
* mixing gain
* volume automation
* comment markers (?)

Some edge cases which could be looked into:
* misaligned left/right channels set as one track
* small slices of audio cut from a larger piece such that all pieces reference the same .au file.


How to use
----------
With python 3.6 or later, run from command line: `python aup2rpp.py myProject.aup` and a .rpp file and audio folder will be saved to the same directory as your audacity project file, with names based off audacity's. Audacity project and files are not deleted, don't worry.


My fork
------
The original project seems to be abandoned so I won't bother making pull requests. So far I've added the following features.

* Defaults all audio files to 32-bit float to avoid clipping issues.
* Avoids duplicate audio files when a sample is repeated.

TODO
-----
* drop silences
* accomodate misaligned left-right channels
* force 16 bit option
* force 32 bit option
* noclip option
* specify output file and output folder.
* dithering when downsampled
