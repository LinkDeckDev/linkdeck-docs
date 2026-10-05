# LinkDeck Glossary

This glossary defines recurring public terms used across the LinkDeck documentation.

It is intentionally product-level. Internal implementation names, security mechanisms and production-specific engineering terminology are excluded.

## AMOLED

A display technology where pixels emit their own light. LinkDeck currently targets a small AMOLED touchscreen, which is one reason the UI direction favors dark backgrounds and limited large bright areas.

## Bring-up

The first stage of validating real hardware: confirming that the board powers correctly and that essential subsystems such as display, touch and communications can be exercised reliably.

## Build in public

The LinkDeck approach of sharing selected progress, devlogs, prototype milestones, lessons and public-safe technical documentation while keeping production-critical engineering private.

## Context Menu

A compact menu opened by a long press in the current interaction direction. It provides contextual navigation such as Home, Profiles, Settings or About without becoming the primary navigation model.

## Digital preparation

The current pre-hardware phase where documentation, UI/UX planning, validation criteria, project infrastructure, branding and implementation planning are prepared before physical prototype testing begins.

## Dynamic QR

A planned future feature where QR content can be generated or changed dynamically rather than remaining a fixed test/static representation. It is not required for the first validated prototype.

## ESP32-S3

The microcontroller family used by the current LinkDeck prototype platform. The selected development board integrates the ESP32-S3 with the display/touch hardware used for early validation.

## Hardware validation gate

A decision point that cannot be finalized responsibly until measured on the physical prototype. Examples include touch thresholds, display brightness, QR scan behaviour, NFC positioning, power use and thermal behaviour.

## LinkDeck

A compact, touch-first device being developed for selecting and sharing digital identities using NFC, with QR as a fallback method.

## LVGL

An embedded graphics/UI framework. The current LinkDeck firmware direction uses LVGL for the touchscreen interface.

## Mock data

Controlled test data used to exercise UI and application behaviour before all real hardware/services are integrated. Mock results are development aids and are not treated as proof of physical functionality.

## Multi-profile

The concept of keeping more than one selectable digital identity on the device, for example Personal, Developer or Business profiles.

## NFC

Near Field Communication. It is the primary sharing interaction in the current LinkDeck product direction.

## NFC state

A user-visible stage of the NFC sharing flow. The current public model includes Ready, Detecting, Success, Timeout and Error.

## OTA

Over-the-air firmware update capability. OTA support is a planned future software feature and is not part of the minimum first physical prototype milestone.

## Profile

A selectable digital identity presented by LinkDeck. A profile may eventually point to destinations such as a website, contact information, GitHub, social links or a portfolio.

The exact production storage and provisioning format is intentionally not public.

## Prototype

A development device used to validate assumptions. A LinkDeck prototype should not be interpreted as a production-ready device or final specification.

## QR fallback

The QR-code sharing path available when NFC is unavailable, inconvenient or unsuccessful. QR is treated as a first-class fallback rather than a hidden emergency option.

## Quick Share

A planned improvement intended to reduce the number of interactions required to share a selected profile. Exact behaviour remains subject to later validation.

## Ray

The LinkDeck manta-ray mascot. Ray is primarily used for branding, welcome, community and selected empty/milestone states rather than dominating functional UI screens.

## Share flow

The user journey that starts from a selected profile and leads to a sharing method, currently centered on NFC with QR available as fallback.

## ST25DV04KC

The NFC device family currently targeted for the final LinkDeck NFC direction. Final behaviour remains dependent on physical prototype validation.

## Touch-first

A design approach where the primary interface is built around direct touch interaction, with generous targets and a deliberately small gesture set.

## Validation-first

The project principle of avoiding final claims or frozen hardware-dependent decisions until they have been observed and measured on real hardware.

## Web Configuration Panel

A planned future browser-based configuration experience. It is an extension to the base product and not required for the first physical prototype.

## Related documents

- [Project Overview](project-overview.md)
- [Public Architecture Overview](public-architecture-overview.md)
- [Software Architecture Overview](software-architecture-overview.md)
- [NFC & QR Sharing Concept](nfc-qr-sharing-concept.md)
