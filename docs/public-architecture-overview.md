# LinkDeck Public Architecture Overview

This document describes the current **public, product-level architecture** of LinkDeck.

It is intentionally broader and less detailed than the internal engineering specifications. Production firmware structure, provisioning, security internals, manufacturing data and other clone-enabling implementation details are not documented here.

> LinkDeck is still in prototype development. Architecture described here is a direction for validation, not a claim that every subsystem has already been proven on physical hardware.

## System goal

LinkDeck is being designed as a compact, touch-first device for selecting and sharing a digital identity.

The current prototype direction combines:

- An ESP32-S3 based controller
- A 1.64-inch 280 × 456 px AMOLED touchscreen
- Capacitive touch input
- NFC as the preferred contactless sharing method
- QR as a universal fallback
- Local profile selection and navigation
- USB-C operation during early validation

The final NFC target is based around the ST25DV04KC family, subject to physical prototype testing.

## High-level architecture

The public architecture can be viewed as four logical layers.

### 1. Interaction and presentation

This layer contains the screens and reusable visual components the user interacts with.

Its responsibilities include:

- Rendering the current profile
- Handling touch feedback
- Showing Share, NFC and QR states
- Displaying settings and device information
- Presenting errors and recovery actions clearly

The UI direction uses LVGL and is designed for a small portrait AMOLED display.

### 2. Application state and navigation

The application layer decides **what the device is doing**, independently of how the hardware performs that action.

It tracks concepts such as:

- Current screen
- Selected profile
- Previous/parent screen
- Current sharing state
- Temporary success, timeout or error state

Navigation is intended to be explicit and predictable rather than being controlled independently by individual widgets.

### 3. Device services

Service boundaries isolate product behaviour from low-level hardware details.

At a public level, these services cover areas such as:

- NFC sharing
- Local profile/settings storage
- Display/device behaviour
- Future connectivity-dependent features

The UI requests behaviour from these services and reacts to their results. It should not directly manipulate hardware buses or device drivers.

### 4. Platform and hardware

The platform layer connects the application to the physical prototype.

It includes responsibilities such as:

- Display output
- Touch input
- Board-specific configuration
- NFC hardware access
- Power and device-level behaviour

The exact implementation remains private and will evolve as the real hardware is validated.

## Core user path

The first prototype is centered around a short interaction path:

**Home → Profile → Share → NFC**

with a fallback path:

**Share → QR → Scan**

A long press provides contextual Back/Menu behaviour, while horizontal swipes are reserved primarily for moving between sibling profiles.

## Profile model

A LinkDeck profile represents one selectable digital identity.

At a product level, a profile may contain:

- A display name
- A profile type
- A visual identity/icon
- One or more destinations to share

The internal storage representation, serialization format and provisioning model are intentionally not part of the public architecture at this stage.

## Offline-friendly foundation

The base LinkDeck experience is being designed so that navigation and locally available profiles do not require a permanent network connection.

Connectivity is reserved for features that genuinely need it, such as future configuration or update workflows.

This keeps the core interaction responsive and reduces unnecessary dependencies during the first prototype phase.

## Validation-first architecture

Several implementation details are deliberately left open until physical testing, including:

- Touch thresholds
- Long-press timing
- Animation timing
- Display brightness defaults
- QR scan brightness behaviour
- Frame-rate targets
- Memory/buffer strategy
- Power impact of UI behaviour

The project follows a simple rule: **measure on the real prototype before freezing hardware-dependent behaviour**.

## Planned extension points

The base architecture is intended to remain compatible with later software additions such as:

- Multi-profile + Quick Share improvements
- Dynamic QR
- Web Configuration Panel
- PIN / Private Profiles
- OTA Firmware Updates
- Themes

These are planned extensions, not requirements for the first physical prototype.

## Public/private boundary

This overview intentionally does not disclose:

- Production firmware source structure in full
- Low-level NFC implementation
- Provisioning or credential handling
- Security/key-management design
- Production storage formats
- PCB/Gerbers or manufacturing files
- Supplier-sensitive information

Public documentation will become more detailed as interfaces are validated and can be documented without exposing production-critical engineering.

## Related documents

- [Project Overview](project-overview.md)
- [Software Architecture Overview](software-architecture-overview.md)
- [NFC & QR Sharing Concept](nfc-qr-sharing-concept.md)
- [UI/UX Overview](ui-ux-overview.md)
- [Prototype Validation Overview](prototype-validation.md)
