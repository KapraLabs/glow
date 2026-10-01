# Measured results

**Status:** 1 October 2026. Figures below are KapraLabs measurements. This file does not describe how the runs were driven.

An outside party cannot reproduce the system from these numbers. They also cannot independently verify them until the same runs are repeated by someone else. Treat every figure as our measurement.

## Glow answer rate

"Answers per second" is the number of replies the run delivered, divided by the length of the run. "Correctness" is the share of those replies our checker marked correct. It is not an independent human evaluation.

Passing hour-long runs:

| When (UTC) | Length | Answers delivered | Answers per second | Average latency | Correctness | Recorded errors |
|---|---|---:|---:|---:|---:|---|
| 27 Sep 2026, 22:17 | 1 hour | 19,827 | 5.5 | 5.8 s | 96.0% | none in the recorded classes |
| 28 Sep 2026, 05:43 | 1 hour | 14,222 | 4.0 | 6.8 s | 96.3% | none |
| 29 Sep 2026, 03:57 | 1 hour | 340,209 | 94.5 | 1.0 s | 96.5% | none |
| 29 Sep 2026, 17:53 | 1 hour | 186,355 | 51.8 | 2.1 s | 96.6% | none |
| 29 Sep 2026, 22:14 | 1 hour | 441,180 | 122.6 | 1.5 s | 96.4% | none |

The 122.6 figure is the highest hour-long passing run in this set. Earlier passing hours were much slower. The rate depends on the conditions of that run. It is not a guaranteed floor.

Passing six-minute runs on 29 September 2026:

| When (UTC) | Length | Answers delivered | Answers per second | Average latency | Correctness |
|---|---|---:|---:|---:|---:|
| 23:26 | 6 minutes | 106,030 | 294.5 | 0.78 s | 96.5% |
| 23:48 | 6 minutes | 104,119 | 289.2 | 0.77 s | 96.5% |

Recorded error classes on the hour-long passes were authentication, backpressure, balance, timeout, sync, and other. All of those counts were zero on the runs in the table. That is a property of those runs, not a claim that the service never returns an error.

## Glow scenario check

On 30 September 2026 a scenario run passed overall:

- Known questions returned the expected answers.
- New questions produced stored answers.
- Asking those new questions again returned the same answers.

This was a correctness check, not a capacity test.

## Price

| Item | Figure | What it is |
|---|---|---|
| AI prompt | $0.002 | Published price per prompt |
| Other billable user operation | $0.002 | Published flat price |
| Multi-recipient payment (up to 1,000 recipients) | $0.002 for the payment | One fee for that payment |

Infrastructure cost per user was not measured.

## Not yet measured

| Topic | Status |
|---|---|
| Glow versus a conventional model API | Not measured |
| Memory use on device or server | Not measured |
| Compute use | Not measured |
| Bandwidth per answer | Not measured |
| Behavior at 100 devices and at 1 million devices | Shape only; not a measured deployment |
| Cost of the privacy rules, in latency or bytes | Not measured |
| Operator cost per user | Not measured |
| Chain transactions per second | Not published |
| Block finality time | Not published |
| Validator hardware, as a measurement | Not measured. Phones confirm; servers write blocks. No hardware benchmark is published here. |
