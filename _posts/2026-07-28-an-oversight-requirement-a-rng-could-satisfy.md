---
layout: post
title: "An Oversight Requirement a Random Number Generator Could Satisfy"
date: 2026-07-28 00:00:00 +0000
---

*A one-line test for rules that mandate human oversight, and the two requirement
elements that no capability and no noise source can supply.*

There is a one-line test for any rule that mandates human oversight of an automated
system: could a random number generator satisfy the requirement as written? Read the
requirement, replace the human with a source of noise that approves at some rate,
interrupts on some schedule, and occasionally escalates, and ask whether the system
remains compliant. If it does, the requirement was never protecting anything. It was
mandating presence, and presence is the one property of oversight that costs nothing to
counterfeit.

The diagnosis behind this test is not new, and the people who own it should be read
first. Ben Green surveyed dozens of policies requiring human oversight of government
algorithms and found the humans cannot perform the functions the policies assign them,
so the mandates function as legitimation: the flawed system ships, now wearing a human
signature ([Green 2022](https://www.sciencedirect.com/science/article/pii/S0267364922000292)).
Ben Wagner called the resulting arrangements quasi-automation, systems that keep a
human in the loop as a rubber stamp precisely so that the loop escapes the legal
category of a fully automated decision
([Wagner 2019](https://onlinelibrary.wiley.com/doi/full/10.1002/poi3.198)). The
empirical flank keeps filling in: overseers exhibit automation bias, defer to the
system they are supposedly checking, and in some settings a human in the loop makes
outcomes worse. None of this needs restating. What needs stating is why the standard
repairs still fail the one-line test, and what would pass it.

The standard repairs strengthen the human. Give the overseer epistemic access, causal
power, self-control, and fitting intentions, and the arrangement counts as effective
oversight; the most careful version of this capacity framework is
[Sterz et al. 2024](https://dl.acm.org/doi/10.1145/3630106.3659051).
Meaningful-human-control accounts add a tracing condition: some human in the chain must
properly understand the system and acknowledge being a legitimate target of blame
([Santoni de Sio and van den Hoven 2018](https://www.frontiersin.org/articles/10.3389/frobt.2018.00015/full)). These are real improvements, and they are still requirements on the overseer's
capacities and self-understanding, not on their exposure. A maximally capable overseer
with nothing at stake passes every capacity condition and remains an excellent rubber
stamp, and acknowledging oneself as a blame target is compatible with a career in
which no miss has ever cost the acknowledger anything. Capacity can be present,
awareness can be sincere, and the requirement can still be satisfied by an arrangement
in which oversight failure lands on no one who signs.

Here is the part I have not seen stated as doctrine, though the evidence for it has
been accumulating in an adjacent field for decades. A substantial fraction of what
oversight measurably contributes may not be judgment at all. It may be perturbation.
Every study that finds human feedback improves an automated process measures against
the same baseline, no feedback, and that baseline cannot distinguish the value of the
overseer's intelligence from the value of being interrupted at all. Optimization has
known this forever: random restarts rescue search from local minima, and nobody credits
the random number generator with judgment. Programmers have known it as folklore since
before the field had a name, because explaining a bug to a rubber duck fixes it, and
the duck contributes cadence, not insight. Oversight research has never run its placebo
arm. Until it does, every measured benefit of a human in the loop is an unresolved
mixture of two things with opposite policy implications: a component you could buy from
a noise source at the price of randomness, and a component that exists only because a
particular party holds the criterion and eats the miss.

Institutions that take oversight seriously already split the mixture, and it is worth
noticing how they do it. Risk-limiting election audits draw ballots at random. Tax
authorities audit at random. Athens allocated most public offices by lot. In every
case, the randomness is the mechanism and never the authority: the lottery decides
which ballots get checked precisely so that no official's discretion can be captured,
while the decision that elections shall be audited, to what confidence level, and what
happens when the audit fails, is owned by a named institution that answers for it.
Noise inside an owned criterion is mature oversight design. Noise as the criterion is
nothing at all. The institutions that use randomness best are the ones that would never
mistake it for an overseer.

So the requirement worth writing has two elements, and neither is presence. First,
criterion ownership: a named party holds the success criterion, including the right to
revise it, and that right is located, not distributed into a diagram where every box
can point to another. Second, outcome-bearing: the owning party can be worse off when
oversight misses, in a way that arrives without anyone's cooperation. The audit
question that operationalizes both is short: who was worse off at the last miss? An
arrangement that cannot answer with a name has automated its oversight already,
whatever the org chart says. And the one-line test returns as the falsifier: a random
number generator can be present, can interrupt, can escalate at a calibrated rate, and
can even improve outcomes. It cannot own a criterion, because a source whose misses
land on no one can administer a standard but not own one. Any requirement an RNG could
satisfy has confused the part of oversight that was always automatable with the part
that is not an input at all.

The practical consequence is a reallocation, not a retreat. If part of oversight's
benefit is perturbation, buy it as perturbation: randomized checks, scheduled
interrupts, sortition-shaped review rosters, all cheap, all capture-resistant, all
already best practice somewhere. Spend the scarce thing, a human who owns the criterion
and bears its misses, exactly where noise fails, on deciding what the system is for,
noticing that the criterion itself has rotted, and answering for the miss no
enumeration foresaw. Presence can be automated. Capacity can be simulated. Perturbation
can be randomized. What cannot be conjured, by any capability at any price, is a party
with something to lose, and oversight requirements should be written for exactly that
element, because it is the only one the machines cannot supply.

---

*The decomposition behind this essay, including the placebo-arm experimental design and
the property-rights argument for why criterion ownership is not an input, is developed
in [a working paper](https://jongsun.dev/papers/grounds-frames-standing/).*
