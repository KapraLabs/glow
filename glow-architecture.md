# Glow: a private AI that lives with the person using it

**Status:** public draft, 1 October 2026. This paper describes behavior and measured results. It is not an implementation specification.

## What a conventional assistant does

A typical assistant is a service. The person sends text to a company. The company runs a model in its own computers, keeps the conversation, and decides who else can see it. The person's access depends on that company's account, price, and retention rules.

That model is simple, and it concentrates memory, identity, and cost in one operator.

## What Glow does

Glow is Kapra's client for that person's AI. It runs as an app on the person's own device. The mobile store edition is the current shipping client. Desktop and browser clients belong to the same product family.

The split of responsibility is:

- The device holds the person's keys and the private side of their AI.
- The Kapra network does the heavy model work and returns the answer to the device.
- The person pays a published flat price per prompt, currently $0.002.
- A Glow install can help confirm the network. It does not write the next block. Block writing is a server role.

Glow is not an offline copy of a large model inside every phone. The phone is the person's node for identity, keys, and private memory. The network answers.

## Privacy, as a product rule

Glow separates three kinds of material:

- **Personal.** Sensitive or identifying content stays with that user. It is not reused as shared knowledge.
- **General.** A general answer may be saved and served again only after identifying details are removed, and it is not tied to the user's identity.
- **Dropped.** Harmful content is not kept for reuse.

The public settlement record is there to account for use. It is not a public copy of the person's prompts.

## Memory

Each person has a private memory that stays on their side of the product. Shared memory is a separate store of general answers. A later ask can be served from that shared store when the answer already exists. A new general answer can be added for later reuse. Personal content does not take that path.

## One device, many devices

The shape is the same at every size. Each device is one person's AI. Devices do not become one shared brain, and they do not pool private memory.

| Scale | What the person gets | What the network is for |
|---|---|---|
| 1 device | One private AI, keys on that device | Answers, settlement, confirmation |
| 100 devices | 100 private AIs | The same shared network |
| 1 million devices | A million private AIs | The same shared network, with more people able to confirm it |

The million-device figure is the intended shape. It is not a deployment we have measured.

Diagrams: [traditional AI](./diagrams/01-centralized-ai.svg), [Glow](./diagrams/02-glow.svg), [one device](./diagrams/03-one-device.svg), [one hundred devices](./diagrams/04-many-devices.svg), [one million devices](./diagrams/05-million-devices.svg), [Kapra and Glow](./diagrams/06-kapra-and-glow.svg).

## What it costs to run

A person needs a phone that can run the app. They do not need a GPU or a datacenter account.

The model computation is done by the network. This paper does not publish server sizes, bandwidth budgets, or a cost model for operators. Those measurements are not in the result set yet. See [benchmarks.md](./benchmarks.md).

## Security, at the boundary a user can check

- Account keys are created and kept on the device.
- Personal content is not published into the shared answer store.
- General answers that are reused have identifying details removed.
- The client can take part in confirming the chain. Confirmation is not the same thing as writing blocks.

This paper does not describe algorithms, key formats, or message layouts.

## What we have measured

On 29 September 2026, internal fleet runs of Glow answered at the following rates. The full table, including slower passing hours and the short peaks, is in [benchmarks.md](./benchmarks.md).

- Highest hour-long passing run: **122.6 answers per second**, average **1.5 seconds** to answer, **441,180** answers, internal correctness score **96.4%**.
- Highest six-minute passing run the same day: **295 answers per second**, average **0.8 seconds**.
- A separate scenario run on 30 September 2026 passed: known answers matched, new answers were stored, and asking those new questions again returned the same answers.

These are our measurements. They are not an independent comparison against another lab's model.

## Why the architecture matters

The person keeps their keys and their private memory. The price of a prompt is a flat published number. General knowledge can be reused. Personal knowledge stays personal. More devices add more people who can confirm the network. They do not add more companies in the middle of the conversation.

## Limits of this paper

- It is not enough to reproduce Glow.
- Inference is network-served. A phone is not claimed to run a full foundation model offline.
- Correctness scores come from our checker, not from an outside audit.
- We have not published a head-to-head against a conventional API, or measurements of memory, bandwidth, or operator cost.
- Chain throughput and finality are covered only where we have numbers. Those numbers are not in this draft.
