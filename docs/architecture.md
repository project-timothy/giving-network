# Architecture (starting point)

This mirrors the recommendation in the 2026-09-18 Giving Network memo.
Revise as design decisions actually get made; this file is a starting
point, not a spec frozen in place.

## Money never touches this platform

Every organization using Giving Network is merchant of record on its
own Stripe account. Giving Network integrates via Stripe Connect direct
charges, so Stripe is the licensed money transmitter and this platform
never custodies a donor's payment. This is true for:

- Any organization with its own 501(c)(3) (e.g. AGWM units).
- An individual missionary with no charity of their own, who instead
  routes through one fiscal-sponsor partner (a real 501(c)(3) that
  exercises discretion over the gift, which US tax law requires for the
  gift to be deductible). Giving Network does not become a fiscal
  sponsor itself.

## Module shape

Modeled on Frappe's app/hook pattern: a Python package with a declared
interface, installable per tenant. This repository depends on the
back-office engine's Apache-2.0 contracts package rather than vendoring
engine code, the same way the engine's own optional `[claude]` extra
installs today.

```
core/agents/giving/     # the module itself
docs/                   # architecture and business-model notes
.github/                # CI, issue templates
```

## Business model

- Self-host: free.
- Hosted: a small flat monthly fee (matches the engine's own
  cost-of-hosting model), not a percentage of any gift.
- Optional donor-covered tip at checkout, opt-in, never a default.
