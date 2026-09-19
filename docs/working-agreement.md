# How this team works

This is a small volunteer team spread across time zones. Everything
below exists to protect two scarce things: reviewer attention, and the
ability of someone who has been away for two weeks to pick up work
without a meeting.

Read this once. It should take five minutes.

## The short version

1. Every piece of work is a GitHub issue before it is code.
2. One issue, one branch, one pull request, one squash-merge.
3. Branches live about two days. Not two weeks.
4. CI has to be green. Nobody merges around a red build.
5. You own a directory, not a feature.

## Issues are the board

If it is not an issue, it does not exist. No side conversations that
turn into merged code, no "I just pushed a quick thing."

A good issue says what changes and how you would know it worked. It is
assigned to exactly one person. If nobody is assigned, nobody is doing
it, and that is useful information.

Use the Task template. The "how we will know it is done" field is the
one that matters. If you cannot fill it in, the issue is not ready to
be worked, and saying so in a comment is a real contribution.

## Branches

Branch off `main`. Name it `<issue-number>-short-slug`:

```
git switch main
git pull
git switch -c 14-stripe-connect-webhook
```

Anyone scanning the branch list can then see what each one is for and
which issue it closes.

`main` is protected. You cannot push to it directly, you cannot force
push it, and you cannot delete it. This is on purpose and it will save
somebody's week eventually.

## Pull requests

Open the PR early, even while the work is unfinished. Mark it a draft.
An open draft PR is how the rest of the team sees what you are touching
before there is a conflict to resolve.

Put `Closes #14` in the body and GitHub closes the issue on merge.

One PR does one thing. A PR that fixes a bug, renames a module, and
adds a feature is three PRs wearing a trench coat, and it will sit
unreviewed because nobody has the hour it needs.

Merges are squash-only. The PR title becomes the commit message on
`main`, so write it like a sentence someone will read a year from now.

## Why branches die in two days

Merge conflicts are not really a git problem. They are a staleness
problem. Two people editing the same file three hours apart merge
cleanly. Three weeks apart is a mess that neither of them remembers the
context for.

So the discipline is not clever branching. It is small work merged
often. If a piece of work cannot land inside two days, it is too big and
wants splitting into issues that can.

This matters more here than on most teams, because agent-written changes
touch more files than hand-written ones do. The blast radius is wider,
so the window has to be shorter.

## Own a directory, not a feature

When we split work, we split it along module boundaries. Two people
working in two directories almost never collide. Two people working on
"the donor flow" collide constantly, because a flow runs through every
layer.

`CODEOWNERS` encodes this. When you take on an area, add your line.

## Working with agents

Most of us are driving coding agents rather than typing every line.
That does not change the workflow, but it changes the emphasis:

- **The PR is the review surface, not the transcript.** Nobody should
  have to read your conversation with an agent to review your diff. If
  the diff does not explain itself, the diff is not finished.
- **You are the author.** Your name is on the PR. "The agent wrote it"
  is not a review response.
- **Tests come first on anything touching money.** Not a style
  preference. An agent will happily produce confident, wrong code that
  reads beautifully, and the test is the only thing that catches it.
- **Keep the agent inside your directory.** A prompt that ranges across
  the whole repo produces exactly the sprawling diff this agreement is
  built to avoid.

You can also bring an agent into the repo itself: mention `@claude` in
an issue or a PR comment and it will read the code, answer, or open a
pull request against that issue.

## Meetings

**One call a week, thirty minutes.** Status does not belong there.
Status lives on the board, where someone in a different time zone can
read it. The call is for what a board cannot hold: what is confusing,
what we should not build, who is stuck and has not said so.

**Everything else is async**, in the issue or the PR it concerns.
Decisions made in a chat thread get lost. Decisions made in an issue
comment are still there in March.

If you are going to be out, say so in the issue you are assigned. Being
unavailable is fine. Being silently unavailable is what hurts.

## Review

A review is not a gate you have to get past. It is the second pair of
eyes that catches the thing you stopped being able to see three hours
ago.

Aim to review within a day. A PR waiting three days for review costs
more than the review would have. "Looks good, one question" is a
complete review.

If you disagree with a review comment, say why. Do not quietly change
the code to make the comment go away.
