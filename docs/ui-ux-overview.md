# LinkDeck UI/UX Overview

This document summarizes the current public interaction and visual direction for the LinkDeck prototype.

It is intentionally a product-level overview rather than the complete internal UI specification.

> The interface is still being validated. Layout details, timings and implementation choices may change after testing on the real touchscreen.

## Display target

Current prototype direction:

- 1.64-inch AMOLED touchscreen
- 280 × 456 px
- Portrait orientation
- Capacitive touch
- Dark AMOLED-friendly visual system

## Design principles

The first LinkDeck interface is being designed around a few simple rules:

1. **Fast to share** — the primary sharing flow should require as few actions as possible.
2. **One-handed use** — primary controls should work comfortably on a small portrait display.
3. **Low cognitive load** — show one clear identity or action at a time.
4. **Touch-first** — avoid tiny controls and dense menus.
5. **Offline-friendly** — the core UI should remain useful without requiring a constant network connection.
6. **AMOLED-friendly** — prefer dark backgrounds and avoid unnecessary large bright areas.
7. **Clear feedback** — taps, share actions and errors should always have an obvious visual state.

## Interaction model

The current interaction model is deliberately small:

- **Swipe left/right** — move between profiles or sibling screens
- **Tap** — select or activate
- **Long press** — back/menu context action
- **Vertical scrolling** — only where content genuinely cannot fit on one screen

Critical actions should not depend on hidden edge gestures.

## Primary experience

The intended high-level flow is:

**Home → choose profile → Share → NFC**

With a universal fallback:

**Share → QR → scan**

NFC is the preferred interaction because contactless sharing is central to the LinkDeck concept. QR remains available when NFC is unavailable or inconvenient.

## Profiles

A profile represents one digital identity rather than the entire device/account.

Possible profile categories include:

- Personal
- Developer
- Creator
- Business
- Temporary/event use

A profile may eventually reference destinations such as contact details, websites, GitHub, social links or a portfolio.

The exact supported fields remain subject to firmware, storage and product validation.

## Core screens

The first functional prototype is expected to explore these core screens:

- Boot / welcome
- Home
- Profile detail
- Share
- NFC ready / success / timeout states
- QR display
- Context menu
- Basic settings shell

## NFC flow

The public UX direction currently includes clear states for:

1. Ready
2. Detecting
3. Success
4. Timeout
5. Error / retry

The user should always be able to switch to the QR fallback without navigating through multiple layers.

## QR flow

The QR screen should prioritize scan reliability:

- Large centered QR code
- Clear profile context
- Short instruction
- Minimal surrounding visual noise

Brightness behavior will be tuned only after real power and scan testing.

## Visual direction

The current LinkDeck identity uses:

- Graphite / near-black base
- Cyan `#22D3EE`
- Electric blue `#0EA5E9`
- Near-white `#F8FAFC`

The UI should feel compact, technical and premium rather than overly decorative.

Ray, the LinkDeck mascot, may appear in welcome, empty or milestone states, but should not dominate functional screens.

## Real-hardware validation

When the prototype hardware is available, the interface will be tested for:

- Readability at the real 1.64-inch size
- Comfortable touch-target sizing
- Swipe reliability
- Long-press timing
- One-handed navigation
- QR scan reliability
- Required display brightness
- AMOLED static-content behavior
- UI responsiveness
- Memory use
- Power impact of brightness and animation

These measurements will determine the final interface rather than assumptions made before hardware testing.
