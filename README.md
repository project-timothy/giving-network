# Giving Network

An open, freely available giving and support platform for missionaries
and small ministries who do not have an in-house donor-giving system.

## What this is

- **Open source.** Anyone technical enough can self-host it at no cost.
  A modest hosted option exists for anyone who cannot.
- **No cut of the gift.** The project makes money from a small, flat
  hosting fee, not a percentage of what a donor gives, with an optional
  donor-covered tip at checkout.
- **Never holds funds.** Every deployment routes payment through the
  receiving organization's own merchant account (Stripe Connect direct
  charges), so the platform is never a money transmitter and every
  ministry's books stay under that ministry's own control. An
  individual with no 501(c)(3) of their own routes through a fiscal
  sponsor partner instead.
- **Pluggable.** Built as a module that installs into a back-office
  engine rather than a monolith, so an organization can run only the
  pieces it needs.

Full architecture and business-model detail lives in `docs/`.

## Status

Early. This repository is the scaffold: license, contribution terms,
and the intended module layout. Implementation follows.

## License

AGPL-3.0, with an additional permission under section 7 (see
[LICENSE](LICENSE)) that lets contributions come in without a signed
CLA, on the CiviCRM model. See [CONTRIBUTING.md](CONTRIBUTING.md).
