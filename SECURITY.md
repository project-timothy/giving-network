# Security

This project eventually touches gifts, ledger rows, and payment
integrations. Treat a security report the way you'd treat a real one,
because it probably is.

## Reporting a vulnerability

**Don't open a public issue.** Use GitHub's private reporting instead:
go to the **Security** tab on this repo, then **Report a vulnerability**.
That opens a private advisory only maintainers can see, so the fix can
land before the problem is public.

If GitHub's private reporting isn't working for you, email
floridayze@gmail.com directly.

Include what you'd want to know if you were fixing it: what you found,
how to reproduce it, and how bad it could get if left alone. A proof of
concept is welcome; a live donor's real data is not, not even to prove
a point.

## What's in scope

Anything touching a gift, a ledger row, a donor record, an auth check,
or a payment integration. The project's hard rule is that the platform
never holds donor funds (see `docs/architecture.md`); a finding that
undermines that rule is the highest priority thing you could report.

## What to expect

An acknowledgment within a few days, and a straight answer on whether
it's real, even if the answer is "not yet, we're early and this code
doesn't exist yet." Credit in the fix, if you want it.
