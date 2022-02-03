Audacity to Reaper project converter
=====================================

This is an experimental converter which reads Audacity project files (`.aup`), and converts them to Reaper project files (`.rpp`). Audio data saved by Audacity (ProjectName_data containing `.au` files) is also included in this process, and gets converted to `.wav`.

![screenshot](https://user-images.githubusercontent.com/1311555/44623740-b77dbb80-a8ce-11e8-8c68-a870524f1116.png)

It uses Python 3.6 and has no external dependencies.


Why
----

- I'm primarily doing this for fun, as I realized both softwares used fairly simple formats to store their data
- Easily transfer old Audacity projects to Reaper. 


How to use
----------

You need to install Python 3.6 or later. Then you can use it from the command line, for example:
```
python aup2rpp.py myProject.aup
```

which will save the reaper file and audio dependencies in the same directory as your .aup file.


Sherman's modifications
------
* Defaults all audio files to 32-bit float to avoid clipping issues.
* Avoids duplicate audio files when a sample is repeated.

TODO
-----
* dithering if upsampled
* drop silences
* accomodate misaligned left-right channels (audacity allows left and right tracks to be misaligned, yes)
* force 16 bit option
* force 32 bit option
* noclip option
* specify output file and output folder.
