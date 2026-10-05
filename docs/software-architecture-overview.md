# LinkDeck Software Architecture Overview

This document summarizes the current **public software architecture direction** for the LinkDeck prototype.

It describes responsibilities and boundaries rather than the complete internal implementation. File-level production structure, low-level drivers, provisioning, security internals and private firmware details are intentionally excluded.

> The architecture is still being validated. Hardware-dependent behaviour and performance decisions will be finalized only after the physical prototype is tested.

## Architecture goals

The first LinkDeck software foundation is being designed to be:

- Small enough for an embedded ESP32-S3 target
- Explicit about application state
- Easy to test with mock data
- Independent from specific hardware drivers at the UI level
- Compatible with future features without forcing them into the first prototype
- Responsive on a 280 × 456 px touch display

The current firmware direction is **ESP-IDF + LVGL**.

## Conceptual layers

The software is organized conceptually into the following responsibilities.

### Input and gesture handling

Touch input is translated into simple product-level interactions such as:

- Tap
- Swipe left/right
- Long press

Raw touch behaviour should not directly decide complex application navigation.

### Application state

A central application-level state describes what should currently be shown and what the product is doing.

Public concepts include:

- Current screen
- Previous/parent screen
- Selected profile
- Current NFC sharing state
- Temporary message/error state
- Context-menu visibility

This keeps the UI deterministic and makes it possible to reproduce states during testing.

### Navigation

Navigation owns transitions between product screens.

Examples include:

- Home → Profile Detail
- Home/Profile Detail → Share
- Share → NFC
- Share → QR
- Long press → Context Menu
- Settings subsection → Settings Root

Reusable widgets request navigation actions rather than loading unrelated screens by themselves.

### Screen rendering

Screens compose reusable visual components and render the current application state.

The first prototype direction includes:

- Boot / welcome
- Home
- Profile detail
- Share selection
- NFC state screen
- QR screen
- Settings shell
- About/device information

### Reusable UI components

Common interaction patterns should be implemented once and reused consistently.

Examples include:

- Status/header elements
- Profile card
- Primary and secondary actions
- Settings/list rows
- Temporary feedback
- Waiting/error/empty states
- NFC and QR presentation panels
- Context menu

Exact component names and source layout remain implementation details.

### Service layer

The UI talks to product-level services instead of hardware drivers directly.

Public service responsibilities include:

- NFC sharing behaviour
- Local profile/settings storage
- Display/device behaviour
- Future connectivity support

Services report semantic results back to the application, such as ready, success, timeout or error, instead of leaking low-level device details into the UI.

### Platform layer

The platform layer isolates board-specific behaviour such as display output, touch input and other hardware integration.

This boundary allows the application and UI architecture to remain understandable even if the physical implementation changes during prototype development.

## State-driven NFC UI

The NFC experience is designed as one state-driven flow rather than several unrelated screens.

At a public level, the states are:

**Ready → Detecting → Success / Timeout / Error**

Timeout and error paths should preserve an obvious recovery path, including QR fallback.

## Event-driven behaviour

The preferred architecture uses semantic application events rather than scattering hardware and UI callback logic throughout the codebase.

For example, the application should reason about actions such as:

- Profile selected
- Share requested
- QR requested
- Retry requested
- Long press detected
- Settings opened

The exact internal event API remains private.

## Mock-first development

Before all hardware services are available, most of the UI can be exercised with controlled test data.

The prototype software plan uses concepts such as:

- Static mock profiles
- Simulated NFC outcomes
- Placeholder device information
- Test QR payloads
- Placeholder hardware indicators

This allows layout, navigation and state behaviour to be evaluated independently from unfinished hardware integration.

Mock results must never be presented publicly as physical validation results.

## Hardware integration order

Once firmware work begins on the real board, the public high-level sequence is:

1. Bring up display and touch.
2. Validate LVGL integration.
3. Establish the base visual system and reusable components.
4. Validate application state and navigation.
5. Build the core screens with controlled test data.
6. Integrate NFC and other services incrementally.
7. Tune gestures on the physical touchscreen.
8. Profile responsiveness, memory and power.

This order intentionally separates basic UI correctness from hardware/service complexity.

## Embedded performance principles

The software direction favors predictable embedded behaviour over decorative complexity.

Current principles include:

- Avoid unnecessary full-screen redraws
- Reuse common visual styles
- Keep decorative animation limited
- Avoid unnecessarily large assets
- Prefer event-driven updates where practical
- Measure memory use on the actual ESP32-S3
- Tune frame rate and display buffers only after hardware profiling

## Offline-friendly core

The base UI should be able to navigate and present locally available profiles without requiring continuous connectivity.

Connectivity is treated as an extension for features that need it rather than a prerequisite for the basic sharing experience.

## Future compatibility

The foundation is being kept compatible with later work on:

- Multi-profile + Quick Share
- Dynamic QR
- Web Configuration Panel
- PIN / Private Profiles
- OTA Firmware Updates
- Themes

These extension points should not delay validation of the first physical prototype.

## What remains private

This overview does not publish:

- Complete production source layout
- Driver code or bus-level hardware access
- Production profile/storage serialization
- NFC provisioning implementation
- Credential/key handling
- OTA security implementation
- Production backend/cloud architecture
- Private diagnostic or manufacturing interfaces

## Related documents

- [Public Architecture Overview](public-architecture-overview.md)
- [NFC & QR Sharing Concept](nfc-qr-sharing-concept.md)
- [UI/UX Overview](ui-ux-overview.md)
- [Public Roadmap](public-roadmap.md)
- [Glossary](glossary.md)
