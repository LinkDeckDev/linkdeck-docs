# LinkDeck Project Overview

LinkDeck is a compact, touch-first device being developed for digital identity, NFC sharing and connected experiences.

The project is currently in **digital preparation before hardware arrival**. Public documentation, UI/UX planning, prototype validation criteria, branding and project infrastructure are being prepared before physical bring-up begins.

> LinkDeck is an active prototype project. Hardware, software, specifications and product direction may change as real-world testing progresses.

## Product concept

The core idea is to make sharing a selected digital identity fast and intentional.

The current product direction combines:

- A compact AMOLED touchscreen
- NFC as the primary contactless sharing method
- QR as a universal fallback
- Multiple digital profiles over time
- A touch-first interface designed for one-handed use
- A small portable enclosure

LinkDeck is not intended to replace a smartphone. It is being explored as a focused physical interface for choosing and sharing a digital identity quickly.

## Interaction model

The current interaction model is deliberately simple:

- **Swipe left/right** — navigate between profiles or sibling screens
- **Tap** — select or activate
- **Long press** — back/menu context action
- **NFC** — primary contactless sharing
- **QR** — fallback sharing method

The final timings, touch targets and interaction details will be tuned on the real hardware.

## Current prototype direction

The first validation platform is based around:

- ESP32-S3
- 1.64-inch AMOLED touchscreen
- 280 × 456 px portrait display
- Capacitive touch
- NFC prototype hardware
- USB-C operation during early validation
- Compact custom enclosure

The current enclosure target is approximately **60 × 35 × 15 mm**, with a hard mechanical envelope of **62 × 38 × 17 mm**.

Battery selection is intentionally deferred until real power measurements are available.

## Software direction

The initial prototype focuses on proving the core experience first:

- Boot / welcome
- Home
- Profile navigation
- Profile detail
- Share flow
- NFC states
- QR fallback
- Basic settings shell

After the foundation is stable, the planned software expansion order is:

1. Multi-profile + Quick Share
2. Dynamic QR
3. Web Configuration Panel
4. PIN / Private Profiles
5. OTA Firmware Updates
6. Themes

These are product priorities rather than guarantees of immediate availability.

## Design direction

LinkDeck uses a dark, AMOLED-friendly visual identity with:

- Graphite / near-black surfaces
- Cyan `#22D3EE`
- Electric blue `#0EA5E9`
- Near-white `#F8FAFC`

The product should feel compact, technical, approachable and premium rather than visually noisy.

**Ray**, the LinkDeck manta-ray mascot, is used selectively for branding, welcome states and community-facing material.

## Build in public

LinkDeck is being developed publicly where doing so is useful and responsible.

Public material may include:

- Development updates
- Devlogs
- Prototype milestones
- UI experiments
- Selected technical documentation
- Lessons learned
- Public examples when stable interfaces exist

Production-critical material remains private, including complete firmware, production CAD, manufacturing data, supplier-sensitive information, provisioning/security internals and credentials.

## Current phase

The current priority is to finish digital preparation and keep the project ready for physical validation.

The next major milestone is the arrival and validation of the first prototype hardware and enclosure.

From there, decisions will increasingly be driven by measurements and real prototype behavior rather than assumptions.

## Related documents

- [Public Roadmap](public-roadmap.md)
- [Prototype Milestones](prototype-milestones.md)
- [UI/UX Overview](ui-ux-overview.md)
- [Prototype Validation Overview](prototype-validation.md)
- [Brand Overview](brand-overview.md)
