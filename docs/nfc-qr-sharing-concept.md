# LinkDeck NFC & QR Sharing Concept

This document explains the current **public sharing concept** for LinkDeck.

NFC is the preferred interaction. QR is the universal fallback. The exact payload format, provisioning model and production security implementation are intentionally outside the scope of this public document.

> The sharing flow is still subject to physical validation. Behaviour described here is the intended prototype direction rather than a claim that final NFC behaviour has already been proven.

## Design objective

Sharing should feel deliberate, fast and recoverable.

The user should be able to:

1. Select the identity/profile they want to share.
2. Start the Share flow.
3. Use NFC as the primary method.
4. Switch to QR immediately if NFC is unavailable or inconvenient.

The device should always make it clear what state the sharing process is in.

## Profile-first sharing

LinkDeck is designed around selectable profiles rather than one fixed identity for the whole device.

A profile may represent contexts such as:

- Personal
- Developer
- Creator
- Business
- Temporary/event use

The active profile determines the destination presented through the selected sharing method.

The internal profile format and storage representation remain private and may change during development.

## NFC as the primary method

The intended NFC experience is state-driven.

### Ready

The device indicates that it is ready to share and prompts the user to bring the receiving phone close to the NFC area.

### Detecting

The UI shows that an interaction is in progress without blocking the user with unnecessary animation.

### Success

A short, clear confirmation is shown.

The success state should be brief and should not trap the user in a long animation or confirmation flow.

### Timeout

If the interaction does not complete in the expected window, the user should receive a simple recovery path:

- Retry NFC
- Show QR
- Return to the previous context

### Error

Recoverable errors should expose the same practical options where possible.

The UI should not expose low-level driver or protocol errors directly to the user.

## QR as a first-class fallback

QR is not treated as an afterthought.

The QR screen is intended to prioritize scan reliability with:

- A large centered QR code
- Minimal surrounding visual noise
- Clear profile context
- A short instruction
- Easy return to the previous screen

Any temporary brightness adjustment will only be enabled after real display, power and scan testing.

## Why both methods exist

NFC and QR solve slightly different practical problems.

**NFC** provides the faster, more physical interaction LinkDeck is being designed around.

**QR** provides broad compatibility and remains usable when:

- NFC is disabled on the receiving device
- Device positioning is awkward
- NFC interaction times out
- The receiving platform handles QR more reliably

A robust product should not make the user choose between elegance and reliability, so the current design keeps both paths close together.

## Separation from implementation

The public sharing model deliberately separates user experience from implementation details.

At a high level:

**Selected Profile → Share Request → NFC or QR Service → User-visible Result**

The UI should not need to know:

- How the NFC driver communicates with the physical chip
- How production payloads are provisioned
- How credentials or sensitive identifiers are handled
- How future dynamic destinations are generated

This separation allows the UX to be tested with mock data before every hardware/service layer is complete.

## Validation goals

Physical prototype testing will determine:

- Reliable NFC positioning
- Interaction timing
- Retry behaviour
- Timeout thresholds
- User instructions
- QR size and scan distance
- Display brightness required for QR scanning
- Power impact of the sharing flow
- Whether the enclosure affects NFC performance

Only after these measurements will the final interaction be frozen.

## Future sharing features

The architecture is being kept compatible with later improvements such as:

- Multi-profile + Quick Share
- Dynamic QR
- Private profiles protected by a future authentication step
- Web-based configuration

These features are planned directions and are not required for the first validated physical prototype.

## Security and privacy boundary

This document describes user-facing behaviour only.

It intentionally excludes production provisioning, credential handling, key management, secure update design and other security-sensitive implementation details.

## Related documents

- [Public Architecture Overview](public-architecture-overview.md)
- [Software Architecture Overview](software-architecture-overview.md)
- [UI/UX Overview](ui-ux-overview.md)
- [Prototype Validation Overview](prototype-validation.md)
