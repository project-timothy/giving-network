# Contributing to Giving Network

Thank you for considering a contribution.

## License of your contribution

This project is licensed under the GNU Affero General Public License,
version 3 (AGPL-3.0), with an additional permission under AGPL-3.0
section 7 (see [LICENSE](LICENSE)). That permission follows the same
mechanism CiviCRM has used since 2010: it lets the project accept your
code without a separate Contributor License Agreement.

To submit a contribution, add this three-line header to the top of each
new or substantially modified source file:

```
Copyright (C) <year> <your name or handle>
SPDX-License-Identifier: AGPL-3.0-or-later
Contributed under the Apache-2.0 inbound license granted in LICENSE.
```

That header is the entire process. No CLA, no signature, no separate
form. By adding it and opening a pull request, you license your
contribution to the project under Apache-2.0 in addition to the AGPL-3.0
terms under which it is received, so the maintainers can incorporate it
without a separate agreement. The project as a whole, and your
contribution once merged, is still distributed downstream under
AGPL-3.0.

## Ground rules

- Money-adjacent code (anything touching a gift, a ledger row, or a
  payout) needs tests before it needs features.
- The platform never holds donor funds. Every payment integration goes
  through a model where the receiving organization is merchant of
  record (see docs/architecture.md).
- Open an issue before a large change so the shape can be agreed first.
