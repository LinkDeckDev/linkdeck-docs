# LinkDeck Prototype Validation Overview

This document describes the public validation approach for the first physical LinkDeck prototype.

The complete internal acceptance plan contains detailed test sequences, measurements and engineering notes. This public version focuses on the validation areas and principles that are useful to follow during development.

## Validation principle

**Measure first, freeze later.**

Values that depend on real hardware — including touch thresholds, display brightness, power usage, battery sizing and mechanical tolerances — should not be treated as final until they have been tested on the physical prototype.

## 1. Incoming inspection

When the first hardware arrives, the project will record and inspect:

- Development board condition
- Display and touch surface condition
- Printed enclosure quality
- NFC prototype hardware condition
- Visible damage, warping or manufacturing defects

Photos will be captured before modification or assembly where useful.

## 2. Mechanical validation

The first mechanical checks will cover:

- Front/rear enclosure fit
- Board fit without PCB stress
- Display alignment
- USB-C access
- NFC placement
- Closure reliability
- Ability to reopen the prototype for continued development

The objective is a usable development enclosure, not production-ready cosmetic perfection.

## 3. First electrical bring-up

Initial operation will use USB-C power before any final battery choice is made.

The first electrical checks include:

- Stable boot
- Repeatable firmware flashing/debug access
- No abnormal heat, smell, resets or electrical behavior
- Basic current observations when measurement equipment is available

## 4. AMOLED validation

The display will be tested for:

- Correct initialization and orientation
- Full-screen rendering
- Pixel/display defects
- Practical brightness range
- Stability during extended UI use
- Static-content behavior relevant to AMOLED usage

Final brightness defaults will be selected only after real use and power measurements.

## 5. Touch and gesture validation

The touchscreen will be tested for:

- Tap reliability
- Horizontal swipe reliability
- Long-press behavior
- Edge/corner response
- Accidental gesture suppression
- Comfortable one-handed interaction

Gesture thresholds and timing will remain adjustable until repeated physical testing produces reliable values.

## 6. Base UI validation

The first UI prototype should demonstrate the core product flow:

**Home → Profile → Share → NFC or QR → Home**

Testing will check:

- Boot-to-home behavior
- Profile navigation
- Profile detail access
- Share flow
- NFC/QR access
- Context navigation
- Basic settings navigation

## 7. NFC validation

NFC testing will focus on real-world usability rather than laboratory-only success.

Checks include:

- Reliable communication with the prototype NFC hardware
- Detection by compatible phones
- Practical positioning/orientation
- Performance with the NFC hardware installed inside the enclosure
- Clear UI feedback and a usable retry/fallback path

The enclosure must not make normal NFC interaction impractical.

## 8. QR validation

QR validation will cover:

- Correct on-screen rendering
- Preserved quiet zone
- Scan reliability from real phones
- Practical viewing distance
- Behavior at different brightness levels

Any temporary brightness boost will be justified by measurements rather than assumed in advance.

## 9. Performance and stability

The prototype will be exercised through repeated navigation and extended sessions to look for:

- UI stalls
- Rendering corruption
- Crashes or boot loops
- Progressive memory loss
- Instability when radios are active

The goal is not production certification at this stage, but a stable platform for continued development.

## 10. Power and thermal measurements

Power consumption will be measured across representative states such as:

- Boot
- Idle UI
- Normal navigation
- High display brightness
- NFC activity
- Wi-Fi activity
- Low-power/screen-off behavior where available

Thermal behavior will also be observed during representative extended use.

## Battery decision gate

The final battery will **not** be selected from estimates alone.

Battery selection will follow real measurements of:

- Actual power consumption
- Available enclosure volume
- Charging behavior
- Thermal behavior
- Protection and integration requirements

## First prototype acceptance

The first prototype can be considered suitable for continued development when it demonstrates, at minimum:

- Reliable USB-C boot
- Repeatable firmware development access
- Usable AMOLED display
- Reliable touch interaction
- Functional base UI navigation
- QR sharing on a real phone
- Demonstrated NFC operation
- Acceptable enclosure fit
- Practical USB-C access
- No critical thermal/electrical issue
- Initial power measurements recorded

Passing this gate means the prototype is ready for continued iteration — not that the final production design is frozen.
