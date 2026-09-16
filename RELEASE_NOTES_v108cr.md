# SOUND TERRARIUM v108cr — Built-in Metronome

## What changed

The battery display has been retired.

On the Cardputer ADV, the battery reading was not accurate enough to be
genuinely useful. Rather than keep an uncertain indicator on the screen,
v108cr removes the battery-display code and repurposes that space for
something that belongs naturally in SOUND TERRARIUM's sound-reactive world:
a **built-in metronome**.

## Metronome

Press **B** to start or stop the metronome.

- Default tempo: **120 BPM**
- Tempo range: **40–200 BPM**
- **← / →**: −1 / +1 BPM
- **Hold ← / →**: continuous 1-BPM adjustment
- Default volume: **80%**
- Volume range: **20–100%**
- **↓ / ↑**: volume −10 / +10

While the metronome is active, its BPM is shown in the former battery/status
area. The numeric value is emphasized without overpowering the terrarium.
When volume is changed, the same fixed position temporarily shows a value
such as **80% VOL**, then returns to BPM.

The readout disappears completely when the metronome is stopped. Its
position is independent of **I (Information)**, so hiding or showing the
information overlay no longer moves the BPM/VOL display.

## Sound-reactive behavior

The metronome is not just an extra clock utility. Its click becomes another
sound source for SOUND TERRARIUM: the beat can be picked up by the
audio-analysis path and can shape the terrain.

The metronome also runs independently of the event-SFX system. UFO flight,
beam and other event sounds can play without stopping the beat, and **X**
continues to control event SFX without switching off the metronome.

## Retained from v108cm

v108cr keeps the existing SOUND TERRARIUM world, including:

- sound-generated 8-band terrain
- restrained three-layer ground perspective grains
- temperature-responsive runner colors
- real-world time, weather, Sun/Moon and tide information
- Sunday 9 PM special shooting star
- separate major meteor-shower events
- refined “KIRAAN” shooting-star synthesis
- retro UFO flight, beam and abduction SFX
- IMU tilt interaction and STEP reference
- multi-network browser-based Wi-Fi setup

## Build status

Successfully compiled for **M5Stack Cardputer ADV** with **M5Stack ESP32 BSP
3.3.9** using the default 1.2 MB APP partition:

- Flash: **1,300,975 / 1,310,720 bytes (99%)**
- Free flash space: **9,745 bytes**
- Global RAM: **55,172 / 327,680 bytes (16%)**
- Available for local variables: **272,508 bytes**

Flash headroom remains very limited, so future changes should continue to be
checked against the default partition.

---

**Small device. Small world. BONSAI Spirit.**
