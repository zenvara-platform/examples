# What is the kaizen cycle?

Zenvara takes its name from two roots. **Zen** (禅): to see clearly, without clutter — things as they actually are. **Vara**: the measured standard, the measuring rod. Together: *clarity through truth.* The **kaizen cycle** is that same idea turned on the way you work — see the real situation clearly, measure it honestly, and improve it one small step at a time.

**Kaizen** (改善, "change for the better") is the discipline of continuous improvement. Its engine is **PDCA** — Plan, Do, Check, Act — a loop you turn again and again, each pass making one thing measurably better and locking in the gain so it cannot slip back.

It is not only for engineers. Teams use the same cycle to cut billing errors, speed up onboarding, reduce waste on a production line, or sharpen a hiring funnel. Anywhere you have a goal, a current state, and a way to measure "better", the cycle fits.

## See before you solve

The most-skipped step is the most important one: **go and see** — *genchi genbutsu*, "go to the real place". Before planning a fix, observe the actual work where it happens and gather real numbers. A decision made from the real situation beats a decision made from assumptions, every time. This is both halves of the name at work: the Zen of seeing things as they are, and the Vara of measuring them against a standard.

## The cycle

- **Plan** — grasp the current condition with data, set a measurable target, find the root cause (ask "why?" five times), and design one small, reversible experiment aimed at that cause.
- **Do** — run the experiment on a small scale. Low risk, reversible, observed.
- **Check** — compare the result against the measure. Did it move? What did you learn? Honestly, and without blame.
- **Act** — if it worked, make it the standard so it cannot backslide; if not, keep the lesson and adjust. Then turn the loop again.

## What makes it stick

- **One small step** beats one big leap — small, safe changes compound.
- **Measure before you move** — no baseline, no improvement.
- **Build quality in** (*jidoka*) — fix causes as they surface; do not inspect defects out later.
- **Eliminate waste** (*muda*) — stop doing what does not add value.
- **Standardise every gain** so it cannot slip back.
- **Respect for people** — improve with the people who do the work.
- **Always a next step** — you are never "done"; you name the next improvement.

## A one-page example

Here is one full cycle, captured as an **A3** — the one-page format that holds a whole improvement on a single sheet:

| | |
|---|---|
| **North Star** | Reliable morning reports the business trusts. |
| **Current condition** | The nightly export fails about 3 nights in 10. On-call is paged at 02:00. Nobody knows why. |
| **Target condition** | Zero unattended failures for 4 consecutive weeks. |
| **Root cause (5 whys)** | Fails → an upstream call times out → the call takes longer than 90 seconds under load → there is no retry → the step was written for the happy path only. |
| **Countermeasure** | Add one bounded retry with backoff to that step. Measure the nightly failure rate. |
| **Check** | 0 failures over the next 3 weeks (was 9 in the 3 weeks before). |
| **Standard** | Retry-with-backoff becomes the default for this class of step. |
| **Next cell** | Add a heartbeat alert so a silent stall surfaces in minutes, not at the morning stand-up. |

This is what the **kaizen-cycle** skill produces for you — tailored to your goal, with your numbers.

## Try it in Zenvara

This library ships a runnable companion: the **kaizen-cycle** skill. Open the Studio AI chat and ask it to run the kaizen cycle. It will ask you a few questions, walk you through one disciplined PDCA turn, and write a bespoke A3 roadmap into this library — ending with a recommended next cell and a review cadence.

The roadmap it creates is itself a folio (see *What is a folio?*): living documentation, yours to edit and revisit each time the loop comes around.
