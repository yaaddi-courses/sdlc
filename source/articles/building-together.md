# Building together: standards, history, reviews and pairing

**Covers:** coding standards, version control, code review, pair programming

## Many hands, one codebase {#overview}
Think about what happens when five people write a story in one document with no shared rules. The voice jumps around, edits overwrite each other, and mistakes slip through. Software is almost always built by several people at once, and it faces the same risk. Four practices keep a team's work consistent and safe: agreed rules for how code looks, a recorded history of every change, a second pair of eyes before changes are merged, and working side by side. Let's take them in turn.

## coding standards {#coding-standards}
Coding standards are the agreed rules for style and structure that everyone on the team follows, so the code looks and behaves consistently no matter who wrote it. They cover naming, formatting, how to organize files and which risky constructs to avoid.

Public examples are PEP 8 for Python and the style guides published by large companies. Tools called formatters and linters check many rules automatically, which saves reviewers from arguing about spaces and commas. The goal is not to find the best style but to have one style, so that reading any file feels familiar.

## version control {#version-control}
Version control is a system, most often Git, that records every change to the code over time: who changed what, when and why. You can compare versions, undo a bad change and return to any earlier state.

It also lets people work in parallel. Each developer works on a separate branch, and the changes are merged when ready. The record becomes a source of truth when something breaks, because you can find the exact change that introduced the bug. Commit often, with short messages that explain the reason for the change.

## code review {#code-review}
Before a change is merged, a teammate reads it. That step is a code review. The reader looks for mistakes, unclear parts and departures from the standards. Problems found here cost minutes to fix. The same problems found by users cost far more.

Reviews also spread knowledge and teach. Keep changes small, because reviewers find fewer problems in large ones. One often-quoted study of review practice suggested keeping a review to roughly 200 to 400 lines of code. Be kind and specific, comment on the code rather than the person, and separate "must fix" from "nice to have".

## pair programming {#pair-programming}
In pair programming, two developers work together on the same code at the same time. One, the driver, types. The other, the navigator, watches, thinks ahead and spots mistakes. They swap roles often.

It feels slower, since two people are on one task. In practice it often gives fewer defects, shares knowledge quickly and is a good way to onboard a new colleague. It works best on hard or unfamiliar problems, and less well on routine work.

## A worked example {#example}
Priya changes how discounts are calculated. Let's follow her change.

1. She creates a branch from the main code (version control).
2. She runs the formatter and linter, which fix style problems according to the coding standards.
3. She commits the change with the message "Round discounts to cents before totals".
4. She opens a request for review. Her teammate Ben reads the 60-line change and asks: "What happens when the discount is negative?"
5. Priya adds a check and a test, and commits again.
6. Ben approves, and the branch is merged.

Later, a customer reports a rounding issue. Using the history, the team finds the change in seconds, reads Ben's question and Priya's reply, and fixes the rule in a few minutes. For a tricky pricing rule next week, Priya and Ben sit together and write it as a pair.

## A common mistake {#mistake}
A common slip is using reviews to criticize style that a tool could check. That wastes human attention. Let the formatter handle style, and use the review for logic, safety and clarity.

A second slip is merging huge changes after weeks, with nobody able to review them properly.

## Key points {#key-points}
- Coding standards give the team one consistent style, enforced where possible by tools.
- Version control records every change and allows safe parallel work and easy undo.
- A code review catches problems early. Keep each change small.
- Pair programming shares knowledge and prevents mistakes, especially on hard problems.
