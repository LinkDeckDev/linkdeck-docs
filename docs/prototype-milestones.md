# LinkDeck Prototype Milestones

This document tracks the public milestone sequence for LinkDeck from digital preparation to a validated physical prototype.

Milestones are intentionally defined by **evidence and validation**, not by speculative dates.

## Milestone 0 — Digital foundation

**Status: In progress / largely prepared**

The project foundation includes:

- Central project documentation
- Public/private repository structure
- UI/UX planning
- Brand identity
- Prototype test and acceptance planning
- Content/devlog preparation
- Public documentation baseline

**Exit condition:** the project has enough documentation, public structure and validation planning to begin physical work without inventing decisions on the bench.

## Milestone 1 — Hardware arrival and incoming inspection

**Status: Waiting for hardware**

The first real components and enclosure are inspected before modification or permanent assembly.

Public evidence may include:

- Photos of the received prototype hardware
- Enclosure photos
- Basic dimensional observations
- Visible condition and fit notes

**Exit condition:** hardware is intact and suitable for safe mechanical/electrical validation.

## Milestone 2 — Mechanical dry fit

The development board, enclosure and NFC prototype are checked together without permanent fixing.

Key questions:

- Does the board fit without harmful pressure?
- Is the display aligned with the aperture?
- Is USB-C accessible?
- Is there a viable NFC location?
- Do the front and rear shells close correctly?

**Exit condition:** the mechanical layout is practical enough to continue development and can still be reopened easily.

## Milestone 3 — First electrical bring-up

The board is powered and programmed outside the enclosure first.

Validation includes:

- Stable USB-C power-up
- Reliable flashing/debug path
- No abnormal electrical or thermal behavior
- Basic development workflow confirmed

**Exit condition:** firmware development can proceed repeatably on the real board.

## Milestone 4 — Display and touch validation

The AMOLED and touch interface are tested on real hardware.

Validation includes:

- Correct 280 × 456 portrait operation
- Practical brightness range
- Touch coverage
- Tap reliability
- Swipe reliability
- Long-press behavior
- Readability at the real 1.64-inch size

**Exit condition:** the display/touch combination is usable for the LinkDeck prototype UI.

## Milestone 5 — Base UI prototype

The first functional interface is exercised on-device.

Expected areas include:

- Boot / welcome
- Home
- Multiple mock profiles
- Profile navigation
- Share flow
- NFC and QR routes
- Basic settings shell

**Exit condition:** the documented interaction model can be used reliably enough for continued prototype development.

## Milestone 6 — NFC validation

NFC behavior is validated with real phones and real enclosure constraints.

Validation includes:

- Basic communication/bring-up
- Repeatable phone detection
- Practical positioning/orientation
- Enclosure effect on reliability
- Clear user-facing NFC states
- QR fallback remains available

**Exit condition:** NFC is practical for normal handheld prototype use.

## Milestone 7 — QR validation

The QR fallback is tested directly from the AMOLED.

Validation includes:

- Correct QR rendering
- Preserved quiet zone
- Reliable phone scanning
- Practical scan distance
- Brightness requirements

**Exit condition:** QR can serve as a dependable fallback to NFC.

## Milestone 8 — Performance, power and thermal measurements

Real measurements replace assumptions.

The prototype will observe:

- UI responsiveness
- Memory stability
- Idle and active power behavior
- Display brightness impact
- NFC/Wi-Fi activity impact where relevant
- Thermal behavior during representative use

**Exit condition:** enough repeatable evidence exists to guide later battery, firmware and enclosure decisions.

## Milestone 9 — Enclosed functional prototype

The validated hardware is assembled into the prototype enclosure and key tests are repeated.

The assembled unit should preserve:

- Display alignment
- Touch reliability
- USB-C access
- NFC practicality
- Basic UI flow
- QR scanning
- Mechanical reopenability for development

**Exit condition:** the enclosed device behaves substantially like the open-bench prototype without introducing a critical issue.

## Milestone 10 — First prototype accepted for continued development

The first prototype can be considered accepted for continued development when:

- USB-C boot is reliable
- Firmware can be flashed/debugged reliably
- AMOLED and touch are usable
- Base UI navigation works
- QR works on a real phone
- Prototype NFC works on real hardware
- Enclosure fit is practical
- No critical thermal/electrical issue remains
- Initial power measurements are recorded
- No unresolved critical defect blocks continued work

This is **not** production approval. It is the gate that allows the project to move from feasibility/prototype validation into deeper product refinement.

## Battery gate

Battery selection is deliberately outside the first USB-C acceptance gate.

A battery should only be frozen after:

- Real power consumption is measured
- The actual internal battery envelope is known
- Charging behavior is understood
- Connector/polarity and protection requirements are verified
- Thermal behavior while charging is considered

## Milestone philosophy

LinkDeck follows one rule throughout prototype development:

**Validate before promising.**

A milestone is reached when evidence supports it — not when a date on a roadmap says it should be finished.
