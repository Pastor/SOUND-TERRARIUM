# SOUND TERRARIUM v108bt — Release Notes

## Lightweight JSON parser hardening

- Removed the ArduinoJson dependency and retained the lightweight manual JSON parser to keep the firmware within the default 1.2 MB APP partition.
- Hardened JSON object-scope handling so whitespace and pretty-printed JSON do not break object lookup.
- Fixed tide-array parsing so `null` values still consume their array position as `NAN`, preventing tide times and sea-level values from becoming misaligned.
- Tide calculations skip non-finite values safely.
- Added JSON string escape decoding, including `\uXXXX` Unicode escapes, standard JSON escapes, and valid UTF-16 surrogate pairs. This improves display of city and country names containing escaped Unicode characters.

## Battery status display and monitoring

- Added battery status display with **BAT OK / BAT LOW / BAT CRIT** states.
- **BAT OK** is shown with the auxiliary information display, while **BAT LOW** and **BAT CRIT** remain visible as warnings.
- Battery monitoring uses:
  - 12-sample ADC averaging
  - 5-second sampling interval
  - 3-cycle recovery confirmation
  - LOW / CRIT hysteresis behavior

## Existing behavior

- Weather, WMO condition handling, rain/snow/thunder visuals, Sun/Moon data, lunar phase, tide display, audio/FFT terrain generation, runner behavior, UFO events, STEP counter, and existing controls are unchanged.

## Build size

Compiled with the default 1.2 MB APP partition used for this release:

- Maximum APP size: **1,310,720 bytes**
- Sketch size: **1,309,339 bytes**
- Remaining: **1,381 bytes**
- Usage: approximately **99.89%**

Because the firmware is intentionally very close to the partition limit, this release is treated as code-frozen after review.
