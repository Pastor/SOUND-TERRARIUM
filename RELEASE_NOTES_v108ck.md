# SOUND TERRARIUM v108ck — Release Notes

## Event sound effects 🔊

- Added small, deliberately quiet, retro-style event sound effects,
  generated in real time. No WAV/PCM/MP3 assets are stored in the
  firmware.
- **X**: toggles all event sound effects (SFX ON / OFF). Enabled by
  default.
- The **I (Information)** overlay shows the current **SFX ON** / **SFX
  OFF** state at the lower-right, beside the battery indicator.
- **J (manual jump)**: a very small 8-bit jump chirp. Terrain-triggered
  automatic jumps remain silent.
- **Shooting star**: a short sparkle sound while the star is moving,
  for both the scheduled Sunday 9 PM star and the manual **M** trigger.
- **UFO flight**: a low retro pulse while the UFO enters, exits, or
  returns.
- **UFO beam**: a very quiet rising electronic sound while the beam is
  active.
- **UFO abduction**: a short synthetic "Aaa!" (about 0.86s) when the
  runner begins to rise into the beam.

## Audio architecture

- Microphone RX and speaker TX now share I2S0 in full-duplex mode,
  driven directly through the ESP-IDF I2S API and the ES8311 codec.
  `M5.begin()` / `M5Cardputer.begin()` / `Mic.begin()` / `Speaker.begin()`
  are still deliberately not called, so the existing microphone/FFT path
  is untouched.
- Event SFX is generated and written to the speaker from a small,
  dedicated FreeRTOS task, so microphone capture and terrain generation
  keep running while an effect plays.

## Real-device fixes since the sound effects were first added

Getting simultaneous microphone + speaker output working correctly took
several real-hardware iterations:

- **TX slot format**: the speaker TX channel was initially configured
  mono/LEFT-only, matching the microphone RX side. On real Cardputer ADV
  hardware this produced no sound at all. Setting the TX slot mask to
  `I2S_STD_SLOT_BOTH` (mic RX stays LEFT) was part of the fix.
- **ES8311 clock manager (REG01)**: the codec's clock-manager register
  was still set to the microphone-only value (`0xBA`) inherited from the
  existing mic setup, which left the DAC's internal clock chain off —
  consistent with the total silence observed (including through the
  3.5mm jack, ruling out the amplifier). The fix went through two
  iterations on real hardware:
  - First, REG01 was changed to `0xB5` (M5Unified's official Cardputer
    ADV *speaker-only* register value), which fixed the silence but
    then broke the microphone, since `0xB5` disables the ADC clock
    bits that `0xBA` had enabled.
  - The two values were compared bit-by-bit against the ES8311
    datasheet's REG01 field table. `0xBA` and `0xB5` turned out to
    differ only in independent ADC-clock and DAC-clock enable bits;
    every other bit (MCLK source/enable, BCLK enable) was already
    identical. REG01 was set to `0xBF` (`0xBA | 0xB5`), enabling both
    ADC and DAC clocks together, which restored simultaneous mic RX +
    speaker TX on real hardware.
- **DAC volume (REG32)**: once sound was confirmed working, the DAC
  volume register was lowered from the unity-gain default (`0xBF`,
  M5Unified's reference value) to `0xB0` (roughly -15 dB), since the
  effects were too loud at unity gain. This does not affect the
  microphone, which has a separate volume register.
- **Short effects lingering past their duration**: jump, shooting-star,
  and abduction sounds could keep sounding briefly after they should
  have stopped. The DMA ring buffer (8 descriptors × 124 frames ≈ 992
  samples, about 20.7ms) could still hold non-silent audio if the SFX
  task was briefly delayed, and the I2S TX driver would keep replaying
  that instead of falling silent. The fix flushes about 9 consecutive
  128-sample silent blocks (more than the full ring depth) when an
  effect ends, instead of just one.
- **Shooting-star sound character**: the original shooting-star sound
  repeated one identical 150ms descending sweep six times over 900ms.
  On real hardware this read as a bird call rather than a sparkle. It
  was reworked into 7 short, independently pitched pings (4.4–7.1kHz)
  with irregular gaps (4–25ms apart) and individual decay envelopes, so
  nothing about the pattern repeats predictably. The new pattern was
  confirmed by ear via an offline render of the exact synthesis code
  before being wired into `serviceSfx()`.

None of the above changes touch the microphone/FFT-driven terrain
generation logic itself; each fix was scoped to the speaker/codec/SFX
path.

## Flash headroom

- The central FreeSansBold clock/date/weather display previously linked
  three separate font tables (9pt, 12pt, 18pt). It now uses only the 9pt
  table with M5GFX's fractional `setTextSize()` scaling to reproduce the
  12pt and 18pt sizes, freeing flash headroom for the sound-effect code
  added in this release.

## Build size

The last confirmed compile result, from the v108ce milestone (before the
v108cf–v108ck audio fixes above), was:

- Flash: **1,304,019 / 1,310,720 bytes (99%)**
- Free flash space: **6,701 bytes**
- Global RAM: **54,972 / 327,680 bytes (16%)**

**v108ck build size: pending current compile measurement.** The changes
since v108ce are small (a handful of register values, a short flush
loop, a few small lookup tables), so flash usage is not expected to move
far from the figures above — but this has not been measured and should
not be quoted as the current number until it is.

## Existing behavior retained

- Sound-generated terrain
- Runner animation and UFO behavior
- Weather, time, Sun/Moon, tide, pressure, precipitation probability,
  temperature and humidity display
- Major meteor-shower visual events
- Sunday 9 PM / manual **M** special shooting star, with its warm-yellow
  / white trail behavior (unchanged from v108ca)
- Cardputer ADV built-in microphone support
- IMU tilt behavior
- BMI270 reference step count
- Wi-Fi credential safety improvements and setup portal
- Battery status display and monitoring
- Temperature-responsive runner colors
