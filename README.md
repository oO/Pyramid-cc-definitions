# Pyramid Instrument Definitions

With PyraOS v3.0, Squarp Instruments introduced the concept of instrument definitions to the Pyramid sequencer. This allows users to define and name both notes and Midi 

Currently a single file named `def.txt` can contain up to 8 instrument definitions. This file must be saved to the root of the Pyramid's SD card.

## How this repository is organized

To keep things simple every file should be named after the instrument it defines. Filenames should only contain lowercase alpha-numerical characters and words are separated by dashes ( a-z, 0-9, - ) do not use spaces, or any other characters or accents.

use the complete name of the device, including the vendor name. For example, it's Elektron Digitakt, not just Digitakt. Korg Volca Bass, not just Volca Bass.

```
audiothingies-micromonsta.txt
elektron-digitakt.txt
korg-volca-kick.txt
makenoise-0-coast.txt
waldorf-blofeld.txt
```

## File Format

The Instrument definition format supports naming both cc messages and notes as follow:

```
NAME: <instrument name>
OUT: <midi port (a,b,usb)>
CHANNEL: <midi channel 1-16>
<cc number>: <cc name>
N<note number>: <note name>
```
For example:

```
NAME:BLOFELD
OUT:A
CHANNEL:2
15:LFO1 SHAPE
16:SPEED
68:FILTER
69:CUTOFF
70:RESONNANCE

NAME:TANZMAUS
OUT:B
CHANNEL:10
2:BD ATTACK
64:BD DECAY
65:PITCH
N36:KICK
N37:SNARE
N38:RIM
N39:CLAP
N40:TOMTOM
N41:SP1
N42:SP2
N43:SP3
N44:SP4

NAME:VST
OUT:USB
CHANNEL:16
0:PRESET
1:ATTACK
2:DECAY
3:RELEASE
119:FILTER
```

