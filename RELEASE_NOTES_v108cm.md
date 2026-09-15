# SOUND TERRARIUM v108cm

A small visual-and-sound refinement for the tiny world.

## What’s new

### Ground perspective
The terrain now contains a restrained layer of moving ground grains to give
the scrolling landscape a little more depth.

- 14 grains total: 6 small, 5 medium, 3 large
- 1 × 1 / 2 × 2 / 3 × 3 px
- Approx. 1.0× / 1.7× / 2.7× terrain speed
- A clear band just below the surface keeps the distant ground uncluttered
- Black by day, dark navy by night

The effect is intentionally subtle: it should feel like depth in the soil,
not a new foreground effect.

### Refined UFO flight SFX
The UFO flight sound now uses a faster retro square-wave sweep inspired by
late-1970s arcade flying-saucer sounds.

- Approx. 5.26 Hz triangular frequency sweep
- Approx. 640–1400 Hz with a gentle nonlinear sweep curve
- Generated in real time; no WAV/MP3 asset is stored in firmware
- Used while the UFO enters, leaves, or returns; beam and abduction SFX remain separate

### Refined shooting-star SFX
The special shooting star now uses a longer synthesized sound inspired by a
bright **“KIRAAN”** followed by a quieter sparkling tail.

- Approx. 2.43 seconds
- Generated in real time; no WAV/MP3 asset is stored in firmware
- The visible shooting-star streak still lasts about 900 ms
- The SFX now has its own timer, so the sparkling tail can continue after the
  visible streak fades
- Works with both **M (Meteor)** and the automatic **Sunday 9 PM** event

Existing major meteor-shower events are unchanged.

## Compatibility / build

Built successfully for **M5Stack Cardputer ADV** with **M5Stack ESP32 BSP
3.3.9**.

- Flash: **1,305,283 / 1,310,720 bytes (99%)**
- Global RAM: **55,228 / 327,680 bytes (16%)**

Flash headroom is extremely limited in the default APP partition.

**Small device. Small world. BONSAI Spirit.**
