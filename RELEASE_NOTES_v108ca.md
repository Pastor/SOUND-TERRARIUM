# SOUND TERRARIUM v108ca — Release Notes

## Meteor Update 🌠

- Refined the special shooting star that appears automatically every Sunday at **9:00 PM local time**.
- The special meteor now uses a **longer, gently widening trail** that fades smoothly into the sky for a more romantic shooting-star effect.
- Added **M: Meteor**, allowing the same special meteor to be triggered manually at any time, similar to the existing **U: UFO event** control.
- Under a **fully dark sky**, the special meteor appears in warm yellow.
- Against a **brighter sky**, it appears white for better visibility.
- The Sunday 9 PM event still appears automatically when the current weather is **clear or cloudy**. In rain, snow, thunder, or other non-clear/non-cloudy weather states, that week's star remains unseen.
- The Sunday event remains tied to local time rather than the day/night cycle, so it can still appear at 9 PM during bright summer evenings at high latitudes.
- The same special-meteor behavior is included in both the **Cardputer ADV** and **Web** versions.
- Existing **major meteor-shower events are unchanged**.

This keeps the Sunday meteor as a small weekly surprise while also making the effect available to enjoy on demand.

**For everyone who kept running this week.  
Something good may be waiting for you next week. 🌠**

## Existing behavior retained

- Sound-generated terrain
- Runner animation and UFO behavior
- Weather, time, Sun/Moon, tide, pressure, precipitation probability, temperature and humidity display
- Major meteor-shower visual events
- Eclipse visual refinement
- T / I information overlay behavior
- Cardputer ADV built-in microphone support
- IMU tilt behavior
- BMI270 reference step count
- Wi-Fi credential safety improvements
- Setup portal refinements
- Lightweight JSON parser hardening
- Tide-array parsing fixes
- JSON string escape decoding
- Battery status display and monitoring
- Temperature-responsive runner colors

## Build note

The Cardputer ADV build compiles within the current default app partition.

- Flash: **1,310,643 / 1,310,720 bytes (99%)**
- Free flash space: **77 bytes**
- Global RAM: **54,652 / 327,680 bytes (16%)**
- Available for local variables: **273,028 bytes**

The firmware was compiled successfully and tested on a real Cardputer ADV through M5Launcher.
