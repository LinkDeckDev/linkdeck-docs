# LinkDeck Documentation

Public documentation and development history for LinkDeck.

This repository contains documentation that is safe to publish while the product is still in prototype development.

## Start here

- [Project Overview](docs/project-overview.md) — what LinkDeck is, the interaction model and the current prototype direction
- [Public Roadmap](docs/public-roadmap.md) — high-level development phases and software priorities
- [Prototype Milestones](docs/prototype-milestones.md) — evidence-based gates from digital preparation to the first accepted physical prototype
- [UI/UX Overview](docs/ui-ux-overview.md) — public interaction model, core flows and real-hardware validation goals
- [Public Architecture Overview](docs/public-architecture-overview.md) — product-level system architecture and public engineering boundaries
- [Software Architecture Overview](docs/software-architecture-overview.md) — public software layers, state, navigation and service boundaries
- [NFC & QR Sharing Concept](docs/nfc-qr-sharing-concept.md) — NFC-first sharing flow and QR fallback direction
- [Brand Overview](docs/brand-overview.md) — visual identity, typography, Ray and communication direction
- [Prototype Validation Overview](docs/prototype-validation.md) — public validation approach for mechanics, UI, NFC, QR, power and thermal behavior
- [Glossary](docs/glossary.md) — recurring LinkDeck product and development terminology
- [Devlogs](devlog/) — public devlog index and preparation material

## Current status

LinkDeck is currently in **digital preparation before hardware arrival**.

The public documentation baseline now includes both product-level and technical architecture material before the first hardware validation cycle. Physical bring-up, measurements and hardware-dependent results will be documented only after they have been observed on the real prototype.

## Repository structure

- [`docs/`](docs/) — reviewed public product and development documentation
- [`devlog/`](devlog/) — devlog index and supporting public preparation material

## Documentation approach

The internal LinkDeck documentation is intentionally more detailed than the public set.

Public documents are curated to explain the product, development decisions, architecture and validation process without exposing production-critical implementation details or prematurely presenting unvalidated decisions as final.

## Related repositories

- [`linkdeck`](https://github.com/LinkDeckDev/linkdeck) — main public project overview
- [`linkdeck-examples`](https://github.com/LinkDeckDev/linkdeck-examples) — future examples and SDK/API samples

## Disclosure policy

This repository intentionally excludes production-critical engineering, including:

- Production CAD
- PCB/Gerbers
- Full manufacturing BOMs
- Complete production firmware
- Supplier-sensitive information
- Provisioning and security internals
- Credentials and private keys

Public visibility does not mean all LinkDeck engineering is open source. See [`LICENSE-NOTICE.md`](LICENSE-NOTICE.md) for the current licensing position.

## Status

> Documentation will grow alongside validated hardware, software and public interfaces. Material may change while LinkDeck is under active development.
