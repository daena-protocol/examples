# Pho Saigon — Example Daena Document

A fictional restaurant in Cambridge, MA, used to demonstrate a typical small-business Daena document.

## What this example shows

- **Facts:** name, address, hours, and menu — each one a typed, dated, individually addressable claim.
- **A capability:** `reserve` — agents can book a table without scraping a third-party reservation widget.
- **Render hints:** a title, a primary-field ordering, a call-to-action priority, and an accent color, all consumed by the universal renderer to produce a clean human view.
- **A document-level signature** under the publisher's DID (`did:web:phosaigon.example`).

## How an agent uses this

A user asks: *"Is Pho Saigon open right now, and can they seat four at 7pm?"*

The agent fetches `https://phosaigon.example/daena.json`, verifies the signature against the publisher's DID, reads the `hours` fact for the current weekday, and either declines (closed) or invokes the `reserve` capability with `{partySize: 4, dateTime: ...}`.

No scraping. No hallucination. No "let me check their website" loop. Two HTTP round-trips, one cryptographic check, one structured answer.

## How a human sees this

The same document, fed through `@daena/renderer`, produces a clean restaurant page — title, menu, hours, address, and a single reservation form — auto-styled per the render hints. The restaurant publishes the data once; the page is rendered on demand.

## Notes

- The signature is a placeholder. A real document would carry an ed25519 (or other supported) signature over a canonical serialization of the rest of the document.
- The `https://daena.org/vocab/...` URIs are placeholders for v0; the actual vocabulary URIs are still being defined.
