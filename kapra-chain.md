# Kapra Chain: what the network is for

**Status:** public draft, 1 October 2026. This paper describes roles, economics, and measured behavior. It does not describe how blocks are chosen, how participants are admitted, or how data is stored.

## Purpose

Kapra is the settlement network under Glow and the other Kapra applications. It accounts for payments, stored knowledge, and AI use in one system, with a flat published price instead of an open fee auction.

Glow is the client. Kapra is the network the client settles on. See [Kapra and Glow](./diagrams/06-kapra-and-glow.svg).

## Who does what

| Role | What they do | What they do not do |
|---|---|---|
| Block-producing servers | Write the next block | Run on a phone |
| Checking servers | Check that produced blocks are valid | Replace the person's device |
| Full nodes | Keep a copy of the chain and accept user traffic | Write blocks by virtue of serving traffic |
| Phones, desktops, and the browser client | Hold the user's keys and can help confirm the chain | Write blocks |

Confirmation and block writing are different jobs. A Glow install can join the confirmation side, where the product allows it. It does not become a block producer.

The current launch keeps block writing to servers. Consumer devices widen confirmation. They do not widen who is allowed to mint the next block.

## Applications

Applications on Kapra can be written in KSL, Kapra's own language for on-network programs. This paper does not describe the language's implementation.

User-facing work, including AI prompts, is settled through the network as accounted operations. The public record shows that an operation was settled. It is not a public transcript of a person's AI conversation.

## Performance

Measured Glow answer rates are in [benchmarks.md](./benchmarks.md).

This draft does not state a chain transactions-per-second figure or a block-finality time. Those measurements were not in the Glow result logs reviewed on 1 October 2026. They will be added only from a recorded run.

## Security

- Users hold their own keys on their own devices.
- Servers that write blocks are a different set from the devices that confirm.
- Personal AI content stays with the user. General answers can be reused only after identifying details are removed.
- Harmful content is not kept for reuse.

This paper does not describe the signature schemes, the confirmation rule, or the checks a server performs.

## Economics

Kapra prices user-facing operations with a flat fee, currently **$0.002** per billable operation. The published AI prompt price is the same **$0.002** per prompt.

A multi-recipient payment, up to 1,000 recipients, is one fee. That single-fee rule applies to that payment. It does not mean a large batch of other operations collapses into one charge.

There is no open auction for block space in this price model. The number above is the published price, not a measurement of our infrastructure cost per user.

## Decentralization, stated plainly

Anyone running Glow can hold their own keys and, where the product allows, help confirm the chain. Block production stays with servers. A reader should treat "the phone participates" as confirmation and custody, not as "the phone writes blocks."

## Limits of this paper

- It is not enough to reproduce Kapra, KSL, or the validator software.
- It does not claim a measured finality time or a measured chain throughput.
- Consumer confirmation and server block production are easy to confuse. The table above is the distinction that matters.
