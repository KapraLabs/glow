# Glow and Kapra

Glow is a private AI client. The person's keys and private memory stay with their device. Kapra is the network that answers, settles a flat fee, and lets devices help confirm the chain.

Block writing is done by servers. A phone does not write blocks.

This repository is a product description. It is not an implementation, and it is not a guide to rebuilding Glow or Kapra.

## Read

- [Glow](glow-architecture.md) — what the client does, and what it does not claim
- [Kapra Chain](kapra-chain.md) — what the network is for
- [Measured results](benchmarks.md) — figures from our runs, and the rows we have not measured
- [Product status](ROADMAP.md)

Diagrams are in [diagrams/](diagrams/).

## Price

A prompt is **$0.002**. Other billable user operations use the same flat price. A multi-recipient payment, up to 1,000 recipients, is one fee.

## Privacy

Personal or identifying content stays with that user. A general answer may be reused only after identifying details are removed. The public settlement record is not a copy of the person's prompts.

## Status

The mobile client is the current store edition of Glow. Desktop and browser clients are part of the same product family.

Product site: [kaprachain.com](https://kaprachain.com)

## What this repository will not contain

Implementation source, consensus rules, storage formats, message layouts, and benchmark harnesses are not published here.
