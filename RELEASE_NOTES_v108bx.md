# SOUND TERRARIUM v108bx — Release Notes

## Eclipse visual refinement

- Refined the compact Sun/Moon astronomical model used for eclipse visuals.
- Improved lunar latitude handling so an ordinary new Moon is no longer shown as a solar eclipse.
- Solar eclipse artwork is now gated by both new-Moon alignment and lunar-node proximity.
- Lunar eclipse coloring is likewise limited to full-Moon alignment near a lunar node.
- This remains a visual approximation for the tiny display, not a local eclipse-path calculator.

## Existing behavior retained

- Sound-generated terrain
- Runner animation and UFO behavior
- Weather, time, Sun/Moon, tide, pressure, precipitation probability, temperature and humidity display
- T / I information overlay behavior
- Cardputer ADV built-in microphone support
- IMU tilt behavior
- BMI270 reference step count
- Wi-Fi credential safety improvements
- setup portal refinements
- lightweight JSON parser hardening
- tide-array parsing fixes
- JSON string escape decoding
- battery status display and monitoring
- temperature-responsive runner colors
