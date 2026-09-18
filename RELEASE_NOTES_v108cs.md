# SOUND TERRARIUM v108cs --- Release Notes

## Tiny Airplane in the Living Sky ✈️

v108cs adds a new ambient detail to SOUND TERRARIUM: a **tiny distant
airplane** that occasionally crosses the sky.

This is intentionally not a conventional game event. There is no
announcement, score, sound effect, or large animation. The airplane is
designed to remain part of the scenery --- something you may simply
notice while the terrarium is running.

### Tiny ambient airplane

-   Appears automatically only **a few times per day**
-   Automatic appearances favor **morning and evening**, with occasional
    daytime passage
-   Travels **left-to-right or right-to-left**
-   Takes roughly **40--60 seconds** to cross the 240 × 135 sky
-   Uses a restrained **10 × 5 px side-on silhouette**
-   Automatic passages are suppressed during **rain, snow, and thunder**
-   Produces **no sound effect**
-   Produces **no on-screen notification**
-   At night, the aircraft body becomes a **dark gray silhouette**
-   A **single bright yellow tail light** blinks slowly at night

The darker nighttime aircraft color was chosen so the single blinking
light remains readable without making the airplane itself visually
dominant.

## Existing features retained

v108cs retains the features introduced and refined in recent releases,
including:

-   Sound-generated terrain driven by the built-in microphone and 8-band
    analysis
-   Restrained moving ground grains for foreground/background
    perspective
-   Built-in metronome with adjustable BPM and volume
-   Retro synthesized event SFX with no stored WAV/MP3 assets
-   Sunday 9 PM special shooting star and separate major meteor-shower
    events
-   Manual meteor and UFO events
-   Real-world local time, weather, temperature, humidity, pressure and
    precipitation probability
-   Sunrise/sunset, moonrise/moonset, lunar phase and tide information
-   Temperature-responsive runner colors
-   BMI270 reference step counter
-   IMU-driven terrain tilt and runner movement
-   Multi-network browser-based Wi-Fi setup
-   Offline fallback behavior

## Build information

v108cs has been compiled successfully for the **M5Stack Cardputer ADV**
using **M5Stack ESP32 BSP 3.3.9**.

-   Flash: **1,301,951 / 1,310,720 bytes (99%)**
-   Free flash space: **8,769 bytes**
-   Global RAM: **55,212 / 327,680 bytes (16%)**
-   Available for local variables: **272,468 bytes**

The firmware still fits the default APP partition, but flash headroom is
now extremely limited.

## Design note

The airplane follows the same design principle as the ground perspective
grains: add life and depth without demanding attention.

The intended moment is not "an airplane event has started," but simply:

> **"Hm? ...oh, an airplane."**

**Small device. Small world. BONSAI Spirit.**
