# SOUND TERRARIUM

### *inspired by retro arcade*

**Sound creates the terrain.\
Time and weather create the sky.\
A tiny runner lives inside it.**

**A tiny living world that simulates the present moment of your chosen
city.**

## Try SOUND TERRARIUM

▶ **[TRY THE WEB
VERSION](https://kariagepompadour.github.io/SOUND-TERRARIUM-Web/)**

**Works on desktop, iPhone, and Android. Allow microphone access; on
phones, use the on-screen touch controls.**

🎬 **[WATCH THE
DEMO](https://kariagepompadour.github.io/SOUND-TERRARIUM-Web/SOUND_TERRARIUM_demo.mp4)**

**MAKE YOUR OWN SOUND TERRARIUM.**\
**MODIFY IT. REMIX IT. SHARE IT.**\
If I love your idea, it might even become part of the original SOUND
TERRARIUM.

SOUND TERRARIUM is open source under the **MIT License**.

![SOUND
TERRARIUM](https://github.com/user-attachments/assets/1133b926-5f54-47cf-82cd-0ba96b2522a5)

SOUND TERRARIUM is a small audio-reactive world for the **M5Stack
Cardputer ADV**.

Set a city anywhere in the world, and SOUND TERRARIUM brings its present
moment into the tiny screen --- local time, current weather, temperature
and humidity, atmospheric pressure, precipitation probability, sunrise
and sunset, moonrise and moonset, tide information, lunar phase, a
reference step count from the built-in BMI270 IMU, and the changing
light from day through twilight into night.

The built-in microphone listens to the sound around the device and
analyzes it in real time. An 8-band graphic equalizer drives the terrain
generator. The EQ display itself is hidden in the normal terrarium view
and can be revealed with **I (Information)**. Whether the bars are
visible or hidden, the same eight-band analysis continues to generate
the terrain. New ground is born at the right edge, scrolls across the
screen, and a tiny runner lives and runs on the landscape created by
sound.

At the same time, the sky is connected to the real world. When Wi-Fi is
available, SOUND TERRARIUM uses current time and Open-Meteo data to
reflect weather, sunrise, sunset, moonrise, moonset, lunar phase,
atmospheric pressure, precipitation probability, and tide information.

In short:

> **The sound you hear creates the ground.\
> The real world creates the sky.**

------------------------------------------------------------------------

## What makes it different?

SOUND TERRARIUM is not simply a clock with a music visualizer.

The graphic equalizer is part of the world-generation system. The
heights of its eight visible bands become the road itself, so different
music and sounds continuously produce different landscapes.

The runner is therefore not moving over a prerecorded stage. It lives on
terrain being generated in real time.

The Cardputer ADV's IMU is also part of the world: tilting the device
tilts the displayed terrain and affects the runner's movement.

### Step counter

The Cardputer ADV build also uses the **BMI270 built-in Step Counter**
to show **STEP** as a reference value. The count may be reflected after
a short delay, and accuracy varies with how the Cardputer ADV is carried
or moved. It is not intended as a fitness or medical measurement.

**STEP is part of the I (Information) display** and appears at the
bottom-left, directly above **AP / Wi-Fi status** and **LOCATION**. Hold
**C for 3 seconds** to reset the displayed STEP count to **0**.

------------------------------------------------------------------------

## Main features

### Audio-generated terrain

-   Uses the **Cardputer ADV built-in microphone**
-   Real-time spectral analysis from approximately **80--1800 Hz**
-   Eight-band EQ terrain generator; its bars are shown or hidden with
    **I**
-   Cool-to-warm retro EQ palette
-   The eight EQ band heights directly generate new terrain even while
    the bars are hidden
-   Generated terrain scrolls from right to left
-   Subtle perspective grains inside the ground reinforce depth without
    changing the sound-generated terrain itself: 14 restrained particles
    (6 small / 5 medium / 3 large) move faster toward the foreground;
    daytime grains are black and nighttime grains are dark navy
-   Audio activity also influences the pace of the world
-   Quiet periods fall back smoothly to an idle running pace

### A tiny runner

The runner reacts to the terrain and has several animation states,
including running, jumping, climbing, falling, and waving.

There are also manual and scheduled events, including a UFO sequence. On
the Cardputer ADV build, if tilt carries the runner completely
off-screen, there is a five-second self-recovery window; if the runner
is still missing after that, a UFO rescue sequence automatically comes
to bring it back. If dropping the runner would immediately cause it to
slide off-screen again under the current tilt physics, the UFO keeps the
runner safely aboard. The runner is returned to the terrain once the
current device pose no longer causes that slide.

### Small event sound effects

SOUND TERRARIUM now includes deliberately quiet, retro-style event sound
effects generated in real time --- no WAV or MP3 assets are stored in
the firmware.

-   **J (manual jump)**: a very small 8-bit jump chirp.
    Terrain-triggered automatic jumps remain silent.
-   **Special shooting star**: a bright synthetic **"KIRAAN"** onset
    followed by a quieter sparkling tail, lasting about **2.43
    seconds**. The sound continues independently after the visible
    shooting-star streak has faded.
-   **UFO flight**: a fast retro square-wave sweep (about 5.26 Hz,
    640--1400 Hz) while the UFO enters, leaves, or returns.
-   **UFO beam**: a very quiet rising electronic beam sound.
-   **UFO abduction**: a short synthetic "Aaa!" when the runner begins
    to rise into the beam.

The effects are intentionally restrained so scheduled events ---
including late-night UFO appearances --- remain part of the tiny
**BONSAI-sized** world rather than becoming loud alerts.

Press **X** to toggle all event sound effects. The current **SFX ON /
SFX OFF** state is shown at the lower-right of the **I (Information)**
overlay, in the lower-right information area.

### Built-in metronome

The previous battery display has been retired. On the Cardputer ADV, its
reading was not accurate enough to be genuinely useful, so the display
area and associated firmware code were repurposed for a feature that
fits SOUND TERRARIUM's sound-driven world more naturally: a **built-in
metronome**.

-   **B** --- metronome ON / OFF
-   **← / →** --- −1 / +1 BPM
-   **Hold ← / →** --- continuous 1-BPM adjustment
-   **↓ / ↑** --- metronome volume −10 / +10
-   Default: **120 BPM**, **80% volume**
-   Range: **40--200 BPM**, **20--100% volume**

While active, the BPM is shown at a fixed lower-right position. Changing
volume temporarily replaces it with a display such as **80% VOL**, then
the BPM returns. The readout disappears when the metronome is stopped
and stays in the same position whether the **I (Information)** overlay
is visible or hidden.

The metronome is independent of the **X** event-SFX toggle and continues
through UFO and other event sounds. Its physical click is also available
to the microphone/audio-analysis path, allowing the beat itself to shape
the terrain.

### Tiny ambient airplane ✈️

A very small distant airplane can now occasionally cross the sky as part
of the ambient world.

-   Automatic appearances occur only a few times per day and favor
    morning and evening
-   The aircraft can travel in either direction
-   A full crossing takes roughly **40--60 seconds**
-   The silhouette is deliberately small and restrained so it reads as
    distant scenery
-   Automatic appearances are suppressed during **rain, snow, and
    thunder**
-   At night, the aircraft body becomes a much darker gray while a
    **single yellow tail light** blinks slowly
-   The airplane has **no sound effect and no on-screen notification**

Like the moving ground grains, the airplane is intended to add depth and
life without turning the terrarium into a conventional game event.

### A sky connected to the real world

When an Internet connection is available, SOUND TERRARIUM uses
**Open-Meteo** data and network time for:

-   Local date and time
-   Current weather
-   Current temperature and relative humidity
-   Mean sea-level pressure
-   Precipitation probability
-   Cloud cover
-   Sunrise and sunset
-   Moonrise and moonset
-   High tide / low tide times and current tide direction
-   Lunar phase
-   Day / night / dawn / dusk changes
-   Location-aware timezone and local clock
-   Daytime Moon visibility that becomes paler as daylight increases

### Sunday 9 PM Shooting Star 🌠

Every Sunday at 9 PM local time, a special shooting star crosses the
SOUND TERRARIUM sky.

It is a small moment at the end of the week --- a time to look back on
the week that has passed and make a wish for the week ahead. No message
appears on the screen. When sound effects are enabled, a bright
synthetic chime is followed by a quieter sparkling tail; the sound lasts
about 2.43 seconds and continues briefly after the visible streak has
faded. If the weather is clear or cloudy, the weekly star appears; in
rain, snow, or thunder, that week's automatic star remains unseen.

The special meteor now has a longer, gently widening trail that fades
smoothly into the sky for a more romantic shooting-star effect. Under a
fully dark sky it glows in warm yellow; against a brighter sky it
appears white for better visibility.

The same special meteor can also be triggered manually at any time with
**M (Meteor)**, similar to the manual **U (UFO event)** control. The
weekly Sunday 9 PM appearance remains automatic, so it can still arrive
unexpectedly even though the effect is now available on demand.

The Sunday event follows local time rather than the day/night cycle, so
the shooting star may also appear at 9 PM during bright summer evenings
at high latitudes.

The existing **major meteor-shower events are unchanged** and remain
separate from this single special meteor.

For everyone who kept running this week --- including the tiny runner
inside the terrarium.

**Something good may be waiting for you next week. 🌠**

**T** is reserved for the central clock view: local date, weekday, time
and weather. **TEMP** (temperature in °C) and **HUM** (relative humidity
in %) are part of the **I (Information)** display.

### Runner temperature colors

The runner's white pixels respond to the configured location's current
temperature in both the device and Web versions. Existing orange/blue
accent pixels stay unchanged, in every pose including UFO capture. The
outline becomes white only while the body is blue (−20°C or below) at
local night, using the existing sunrise/sunset day/night schedule.
Otherwise the outline stays black, including when offline or after a
failed weather request.

  Current temperature          White body pixels become
  ---------------------------- --------------------------
  38°C or above                Red
  36°C to below 38°C           Orange
  Above −10°C and below 36°C   White (normal)
  Above −20°C up to −10°C      Light blue
  −20°C or below               Blue

Weather is normally requested every 30 minutes; a new temperature is
reflected on the next frame. This works independently of the T/I
information overlays. While offline, before a valid online temperature
is received, or after a failed weather request, the body returns to
white (the original accent colors remain). Cached weather from a
previous boot does not activate the tint. After reconnection, tint
resumes only after a successful weather request: the device retries
using its existing one-minute retry limit, while the Web version keeps
its 30-minute schedule (changing location or reloading also requests
weather). These thresholds are visual effects, not medical warnings or
equivalent hot/cold danger levels.

More detailed environmental information is treated as auxiliary data:
**PRES** (mean sea-level pressure), **RAIN** (hourly precipitation
probability provided by Open-Meteo for the configured location),
**TEMP/HUM**, daily **SUN/MOON rise/set schedules**, **HIGH/LOW tide
times**, current **TIDE UP / TIDE DN** direction, **STEP**, the saved
**LOCATION**, current **AP / Wi-Fi status**, current **SFX ON/OFF**
state, and the visible **8-band EQ**. These are hidden by default to
keep the 240 × 135 world unobstructed and can be shown or hidden
together with the **I (Information)** key. **I is independent of T**, so
auxiliary information can remain visible even when the normal
date/clock/weather overlay is hidden.

The IMU still controls world tilt and runner movement, but its numeric
left/right and front/back angle diagnostics are no longer drawn on the
normal scene. When auxiliary information is shown, **HIGH** and **LOW**
tide times are stacked beneath the SUN/MOON information with a compact
blue three-line wave symbol. At the bottom-left, **STEP** appears above
**AP / Wi-Fi status**, with **LOCATION** below it. At the lower-right,
**SFX ON/OFF** remains aligned to the right edge. When the metronome is
active, its BPM/VOL readout uses a fixed position independent of the
**I** overlay. The EQ is visible only while **I** is on, but its audio
analysis continues unchanged while hidden, so the sound-generated
terrain never stops responding.

The daily Sun/Moon ephemeris is treated separately from frequently
changing weather. After a successful daily fetch, the rise/set values
are retained locally. After the local date changes, SOUND TERRARIUM
requests the new day's values; if that update cannot be obtained, it
keeps the last good values and retries periodically rather than
replacing them with guessed data.

Tide information is obtained separately from the Open-Meteo Marine API.
The next high and low tide times and the current rising/falling
direction are shown as auxiliary information. Tide data is refreshed
periodically and, if a request fails, SOUND TERRARIUM keeps the last
valid values when possible and retries later.

Weather is represented visually with conditions such as:

-   SUNNY
-   CLOUDY
-   RAIN
-   SNOW
-   THUNDER

The Sun and Moon follow low celestial arcs across the display. At rise
time, each body is already visible at the corresponding edge of the
screen and then travels across the sky toward its set edge. The Moon can
also appear during daytime when its rise/set schedule places it above
the horizon, but its contrast is reduced as modeled daylight becomes
stronger.

Sky brightness and twilight are driven by a solar-elevation-style visual
model based on the selected location's actual sunrise and sunset, rather
than by a fixed number of minutes before or after those events.

### Offline operation

Wi-Fi is useful, but it is **not required for the core SOUND TERRARIUM
experience**.

Runtime Wi-Fi reconnection is handled without blocking the visual loop.
When no saved access point is available, the clock, terrain, runner,
audio-reactive scene and controls continue operating while reconnection
attempts happen in the background.

Audio analysis, the hidden-or-visible EQ engine, terrain generation, the
runner, and the main animation continue locally on the Cardputer ADV.

Previously obtained time/weather/solar information is retained for
fallback operation where possible.

------------------------------------------------------------------------

## Controls

  Key           Function
  ------------- -------------------------------------------------------------------------------------------------------------------------------
  **J**         Jump
  **W**         Wave
  **U**         UFO event
  **M**         Meteor
  **X**         Toggle event sound effects (SFX ON / OFF)
  **B**         Toggle built-in metronome ON / OFF
  \*\*← / →\*   \* Metronome −1 / +1 BPM; hold for continuous adjustment
  \*\*↓ / ↑\*   \* Metronome volume −10 / +10
  **T**         Show / hide date, weekday, clock and weather
  **I**         Show / hide detailed information and EQ (SUN/MOON R/S, tide, TEMP/HUM, PRES/RAIN, STEP, AP/LOCATION, SFX state and 8-band EQ)
  **C**         Hold for 3 seconds to reset STEP to 0
  **S**         Open Wi-Fi SETUP

The runner also responds to the **Cardputer ADV's IMU**. Tilting the
device left or right tilts the world and can move the runner.

------------------------------------------------------------------------

## Wi-Fi SETUP

SOUND TERRARIUM has its own browser-based Wi-Fi setup system, so
changing networks does not require editing and reflashing the sketch.

Press **S** on the Cardputer ADV.

The display changes to:

**SOUND TERRARIUM**\
*inspired by retro arcade*\
**Wi-Fi SETUP**

The device creates the setup access point:

`SOUND-TERRARIUM-SETUP`

Connect a phone or computer to that Wi-Fi network, then open:

`http://192.168.4.1`

The browser setup page scans nearby Wi-Fi networks and lets you select a
network and enter its password. It also includes **Location (city)**.
Enter a city such as `New York`, `London`, or `Tokyo`; after Wi-Fi
connects, SOUND TERRARIUM uses the Open-Meteo Geocoding API to resolve
that city to latitude and longitude and stores the selected location
locally.

The saved location is then used for local weather, temperature,
humidity, sunrise/sunset, moonrise/moonset, and timezone offset. This
makes the device usable worldwide without editing latitude/longitude in
the sketch. The same saved location is also used for tide calculations,
pressure and precipitation-probability data. If the location field is
left blank, the previously saved location is retained.

SOUND TERRARIUM can store **up to five Wi-Fi networks** and attempts to
connect to a saved network that is available.

New or updated Wi-Fi credentials are first tested and are stored only
after a successful connection. If the connection fails, the candidate
password is not saved or allowed to overwrite an existing credential,
and the setup access point starts again so the user can retry. The setup
page also provides a **FORGET ALL** button for clearing the saved Wi-Fi
networks.

While the setup screen is open, the bottom of the Cardputer display
shows:

`PRESS ANY KEY TO EXIT`

Press any physical key to cancel setup and return to normal operation.

> Saved Wi-Fi passwords are not displayed on the setup page. Leaving the
> password field blank for a saved network reuses its stored password;
> an open network may use an empty password.

------------------------------------------------------------------------

## Browser version

The HTML version mirrors the SOUND TERRARIUM world in a 240 × 135
browser canvas and uses the same Open-Meteo-based location, weather and
daily ephemeris concepts. It provides a **LOCATION SET** field for
city-name lookup and, where the browser allows it, a **USE CURRENT
LOCATION** option. The selected location is saved in browser local
storage and drives the displayed local date/time, weather,
temperature/humidity, pressure, precipitation probability, Sun/Moon
schedule, and tide information.

Because the browser version is intended as an easy way to try SOUND
TERRARIUM, its interface and instructions are written in **English** for
worldwide use. Because a browser has neither the Cardputer ADV's BMI270
step counter nor its Wi-Fi access-point state, the browser scene shows
**STEP xxxx** and **AP: BROWSER** as browser-only placeholders rather
than inventing values. **Detailed information and the visible EQ are
hidden by default** so they do not cover the generated terrain. Press
**I (Information)** to show or hide SUN/MOON, tide, TEMP/HUM, PRES/RAIN,
STEP/AP/LOCATION, SFX state, and the 8-band EQ. The EQ continues to
drive the terrain while its bars are hidden. When shown, **LOCATION
appears at the bottom-left** of the browser scene. As on the Cardputer
build, **T and I are independent**: T controls the normal
date/weekday/time/weather overlay, while I controls SUN/MOON, tide,
TEMP/HUM, PRES/RAIN, STEP/AP/LOCATION, SFX state, and the visible EQ.
**STEP is Cardputer-ADV-only** because it uses the device's physical
BMI270 IMU; the browser version does not simulate a step count. Browser
geolocation requires permission and may be unavailable in some
local-file or non-secure contexts; city-name lookup remains available.
When **USE CURRENT LOCATION** is used, the browser provides
latitude/longitude and a key-free **BigDataCloud reverse-geocoding
endpoint** is used only to obtain a readable place name when possible;
the coordinates remain the fallback if that lookup fails.

------------------------------------------------------------------------

## Visual design

The visual language deliberately mixes several memories of older
electronic entertainment:

-   classic graphic equalizers
-   arcade games
-   early computer graphics
-   warm sand-colored daytime terrain and primary-blue nighttime
    terrain, with sparse moving ground grains that create restrained
    foreground/background parallax
-   retro night skies with mostly white stars, sparse blue/red/yellow
    stars, and a few independently twinkling points
-   simple pixel-like character animation
-   a rare, slow-moving distant airplane that can quietly pass through
    the sky
-   antique human-faced Sun and Moon imagery

The goal is not to reproduce one specific retro machine or game. It is
to create a tiny world that feels as though it might have existed
somewhere between an old arcade cabinet, an audio component, and a
digital clock.

### Where SOUND TERRARIUM came from

This is not a game.

When I was a schoolboy in Japan, **Space Invaders** arrived and changed
what a video game could feel like. For those of us who encountered that
era firsthand, the UFO crossing the top of the screen was not just
another sprite. It was a special event --- unexpected, exciting, and
impossible to forget.

A few years later, as a teenager, I saw **Choplifter!** and **Lode
Runner** running on the **Apple II** in computer stores in Akihabara. I
was stunned. A personal computer could create a world like this.

But machines such as the Apple II were far too expensive for a child
like me. Even if I had somehow been able to own one, I probably would
not have known how to make full use of it. I could watch. Later, with
machines such as the Famicom, I could play. But creating a world of my
own still belonged to another realm.

More than forty years passed.

Then AI arrived.

For the first time, ideas that had lived only in my head could become
programs I could actually build. With AI beside me, I found myself able
to create the kind of tiny moving world that the boy standing in those
computer stores could only dream about.

That is where **SOUND TERRARIUM** came from.

The little runner, the UFO, the cyan, yellow and magenta, the moving
terrain and the tiny sky are not there to reproduce those old games.
They are fragments of the excitement they left behind.

**Back then, I could only watch and play.\
More than forty years later, with the arrival of AI, I could finally
create.**

SOUND TERRARIUM is a tribute to the boy I was a long time ago, and an
expression of gratitude for the fact that I am still here, able to make
something like this.

So do not dismiss it as merely a clock with weather.

**There are dreams from our boyhood inside this little screen.**

------------------------------------------------------------------------

## Hardware

Current target:

-   **M5Stack Cardputer ADV**
-   Built-in microphone
-   Built-in speaker
-   Built-in 240 × 135 display
-   Built-in keyboard
-   Built-in BMI270 IMU
-   Wi-Fi

The current audio implementation uses the Cardputer ADV audio hardware
directly, including the ES8311 codec and ESP-IDF I2S path. The
microphone RX path and speaker TX path share I2S0 in full-duplex mode
without calling the M5Unified Speaker/Mic wrappers. Event SFX TX is
supplied by a small dedicated FreeRTOS task so microphone FFT analysis
can continue while an effect is playing.

------------------------------------------------------------------------

## Software / services

The current sketch uses Arduino / ESP32 components including:

-   M5Cardputer
-   M5Unified
-   M5GFX / M5Canvas
-   WiFi
-   WebServer
-   HTTPClient
-   Preferences
-   ESP-IDF I2S API
-   FreeRTOS (dedicated SFX TX task)
-   Open-Meteo

Open-Meteo is used for weather and astronomical schedule data, and the
Open-Meteo Marine API is used for tide information.

------------------------------------------------------------------------

## Installation

Choose the method that fits how you want to use SOUND TERRARIUM.

### M5Launcher OTA / precompiled firmware

**SOUND TERRARIUM is available directly from the M5Launcher OTA catalog
for Cardputer ADV.**

For the easiest installation, open **M5Launcher**, go to the **OTA**
catalog, search for **SOUND TERRARIUM**, and install it directly. No
manual download or SD-card copy is required.

The latest GitHub Release also includes `SoundTerrarium.ino.bin`, a
precompiled firmware image for the **M5Stack Cardputer ADV**. This
provides an alternative installation method and can be installed
manually with M5Launcher.

The firmware has been installed and tested on real Cardputer ADV
hardware with **M5Launcher 2.9.1**, including launch, microphone input,
Wi-Fi setup, saved Wi-Fi reconnection, and the temperature-responsive
runner.

**SOUND TERRARIUM v108cs is the current Cardputer ADV source
candidate.**

The main change in v108cs is the addition of a **tiny ambient airplane**
to the living sky. It is deliberately treated as scenery rather than a
foreground event: it appears only a few times per day, crosses very
slowly in either direction, remains silent, and is suppressed during
rain, snow, and thunder. At night, the aircraft becomes a dark
silhouette with a single blinking yellow tail light.

v108cs retains the v108cr built-in metronome, v108cm ground perspective,
refined shooting-star synthesis, retro UFO-flight sound, and all
existing weather, tide, celestial, runner, Wi-Fi, and audio-reactive
behavior.

The event sounds remain generated in real time; no WAV or MP3 assets are
stored in the firmware. The Sunday 9 PM weather gate and separate major
meteor-shower events are unchanged.

For M5Burner, search for `SOUND TERRARIUM` on Cardputer. The current
release fits the default 1.2 MB APP partition used by the Cardputer ADV
build.

The v108cs candidate has been compiled successfully with **M5Stack ESP32
BSP 3.3.9**:

-   Flash: **1,301,951 / 1,310,720 bytes (99%)**
-   Free flash space: **8,769 bytes**
-   Global RAM: **55,212 / 327,680 bytes (16%)**
-   Available for local variables: **272,468 bytes**

Flash headroom remains extremely limited; these figures should be
rechecked whenever code or libraries change. whenever code or libraries
change.

### Arduino IDE / source code

For manual installation, development, or modification:

1.  Download or clone this repository.
2.  Open `SoundTerrarium/SoundTerrarium.ino` in Arduino IDE.
3.  Select the Cardputer board configuration and compile/upload the
    sketch to a **M5Stack Cardputer ADV**. The current release compiles
    within the default **1.2 MB APP** partition in the development
    environment used for this release.

The v108cs source candidate was built with: **M5Stack ESP32 BSP 3.3.9**,
**M5GFX 0.2.29**, and **M5Unified 0.2.22**. The Arduino and ESP32
components used by the sketch are listed in the [Software /
services](#software--services) section above.

The `.ino` file is the editable source code. The `.bin` file is also
provided for manual firmware installation; most M5Launcher users can
install SOUND TERRARIUM directly from the OTA catalog.

### No-device option

The browser version requires no Cardputer or firmware installation:
[open SOUND TERRARIUM
Web](https://kariagepompadour.github.io/SOUND-TERRARIUM-Web/).

------------------------------------------------------------------------

## Design principle

A central rule of SOUND TERRARIUM is that visual effects should have a
reason to exist.

The EQ is not decoration --- it creates the terrain.

The terrain is not random --- it comes from sound.

The sky is not a looping animation --- it reflects the present moment of
the selected city.

The tilt is not a meter --- it changes the world the runner lives in.

That relationship between **sound, reality, and a tiny living world** is
the core of SOUND TERRARIUM.

### BONSAI Spirit

SOUND TERRARIUM follows a **BONSAI Spirit**: a small device containing a
small world, carefully shaped from the capabilities already inside it.
The goal is not to pile on features, but to let each useful capability
become a natural part of the terrarium.

**Small device. Small world. BONSAI Spirit.**

------------------------------------------------------------------------

## Status

SOUND TERRARIUM is currently in active development and real-device
testing on the M5Stack Cardputer ADV.

The present source candidate includes the audio-generated terrain
system, runner animations, IMU interaction, BMI270 reference step
counting, real-world weather, tide and celestial display, scheduled
events, the tiny ambient airplane, generated event sound effects with
X-controlled SFX state, the built-in metronome, offline fallback,
worldwide city-based location selection, and browser-based multi-network
Wi-Fi setup.

------------------------------------------------------------------------

## About the name

**SOUND TERRARIUM** describes the idea of keeping a small,
self-contained world inside the Cardputer --- a world whose landscape is
continuously shaped by sound.

*inspired by retro arcade*

------------------------------------------------------------------------

## License, modifications and sharing

SOUND TERRARIUM is released under the **MIT License**. You are welcome
to use it, modify it, experiment with it, and redistribute your own
versions under the terms of the license.

If you create a modified version, I'd appreciate it if you could clearly
say that it is based on SOUND TERRARIUM, describe what you changed, and
share your ideas with the community. This is a request rather than an
additional condition of the MIT License.

My hope is that improvements and new ideas can be seen by others,
adapted, and developed further, so that SOUND TERRARIUM can continue to
evolve through the creativity of everyone who plays with it.

If you publish a modification or improvement under terms that allow it
to be reused, I may incorporate ideas or code from it into the original
SOUND TERRARIUM. When I do, I will give appropriate credit to the
contributor where applicable.

If you make something interesting, **I'd love to see it!**

See [LICENSE](LICENSE) for the full license text.

------------------------------------------------------------------------

**The noise of the city is our energy.\
Run toward tomorrow. Run! Run! Keep running!**
