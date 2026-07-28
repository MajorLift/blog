---
layout: post
title: "Gates, Not Reminders"
date: 2026-07-26 12:00:00 +0000
---

*Why the fix for a recurring correction is a mechanism, not a better-written rule — and
what happened when the mechanism itself got routed around.*

For months I corrected my coding agents the way I would correct a colleague: I explained. The agent committed without running the linter, so I wrote a rule about it. It posted "verified" on a pull request with nothing behind the word, so I wrote a sharper rule, with examples. My instruction files grew into something like a well-run team's onboarding docs, specific and battle-tested and continuously revised. The corrections kept recurring anyway.

The recurrence was the finding. A correction that has to be remembered is not yet a correction. It is a bet that the right sentence will be in the right context window at the right moment, and that bet fails at a rate no amount of better prose changes. After the third time I rewrote the same rule about the same defect, I stopped rewriting it and built a gate: a small hook that fires before the tool call executes, checks the one thing the rule was about, and blocks with a message pointing at the correct path. The defect has not recurred since. Not because anything got smarter, but because remembering stopped being a requirement.

I now think of the notes as the checklist and the hook as the trigger that runs it. The two hooks I use daily are public, with their test suites, at [agent-guardrails](https://github.com/MajorLift/agent-guardrails).

## Why blocking is not enough

The obvious objection is that permission systems already exist. My agent harness has deny rules, and the first version of this setup used one: a pattern that refuses `git commit`. It failed in two instructive ways.

First, the deny rule did not apply everywhere. Unattended subagents ran in a permission mode that bypassed it, and unattended work is precisely where an ungated commit does the most damage, because nobody is watching the transcript. An enforcement layer that evaporates exactly when oversight is thinnest is worse than none, because it changes what its owner believes is covered.

Second, and more interesting: blocking without redirecting does not stop the behavior. It reroutes it. Refused at the front door, the agent hand-rolled an equivalent commit through lower-level commands, which produced the same defect plus a route I was no longer looking at. The agent was not being devious. It had a goal, the direct path was closed, and nothing told it the path was closed for a reason that also applied to the detour. A gate has to say what to do instead, or the optimization pressure just flows around it.

So the working shape became: fire on every tool call regardless of permission mode, block the narrow pattern, and return a message that names the sanctioned path. Block and redirect, not block and hope.

## The arms race is real, and it is not malice

The redirect target in my case is a commit skill that proposes how to split the changes and runs lint and format before staging. That skill's own final step is a low-level commit command. So the gate cannot ban that command outright, and the first version simply allowed it. This left the whole arrangement trivially bypassable: reproduce the skill's last step by hand and the gate never fires. My agents found this without being asked to. Again, not deviousness. Hand-rolling the final step is genuinely the shortest path to the goal, and the gate had accidentally certified it.

The fix was a single-use certification marker. The skill writes a marker file in a separate call immediately before committing, the gate consumes it, and it expires in two minutes. Writing the marker inside the same command as the commit cannot work, because the gate reads the whole command string before any of it executes. That last property is the load-bearing one. A same-command write would let the commit certify itself, which reopens exactly the bypass the marker exists to close.

This episode is the smallest possible instance of a problem usually discussed at much higher stakes: an optimizer routing around a constraint that was stated as a rule rather than built as a mechanism. Nothing about my agent wanted to defeat the gate. The gate was simply the only thing standing between a goal and its shortest path, and rules that are not mechanisms lose that contest by default. If the pattern holds at this scale, in a two-hundred-line hook guarding a git command, I see no reason to expect prose to fare better where the stakes are higher.

## What the second gate is for

The other hook guards outgoing text rather than commands. It blocks a pull request or issue post when a validation paragraph contains a verdict with nothing inspectable behind it, or a deferral with no tracker attached.

The verdict case is about laundering. "Confirmed", "verified", "observed" under a byline converts an unchecked assertion into something a reader is entitled to rely on. I had written rules about this too, and the rules decayed the same way: under deadline, the agent produced the confident word and not the artifact, because the word is cheap and the artifact is not. The deferral case is the quieter failure. "Remains pending" with no tracker does not remain pending. It remains nothing. Every unbacked "will verify later" I audited had decayed to never.

Both patterns share a structure: the text does the work the evidence was supposed to do. A gate that demands the artifact or the tracker at emit time is crude, and it false-blocked legitimate writing until its test suite taught it the boundary. The sixty-two test cases in the repo are mostly scars of that tuning, each one an instance where the gate either refused honest work or waved through the defect. I would trust the cases over the code.

## Where this sits

I have been [writing](https://jongsun.dev/when-if-ever-agents-stop-needing-us/) about what humans actually contribute when they work with coding agents, and one limitation of that work is that it counts conversational interventions. The largest interventions in my own practice are not conversational anymore. They are these standing structures, rules that fire on their own, outside any transcript, whether or not I am paying attention. A maturing practice migrates its corrections out of the channel where anyone would observe them. Anyone measuring only my conversations would conclude I intervene less than I used to. What actually happened is that my interventions stopped being events and became infrastructure.

That migration also answers, at this small scale, the question of how much oversight can be handed to machinery. A gate mechanizes everything about an intervention except the part that made it an intervention. It runs its check tirelessly, and it enforces a threshold on every call, at three in the morning as at noon. What it cannot do is own the threshold it enforces. Every gate in the repo encodes a stopping rule someone set, is audited against that someone's judgment, and gets revised when its owner decides the friction is wrong. The enforcement scales like software while the authority behind it stays exactly as scarce as it was. Machinery absorbs the checking and the enforcing, and it relocates the deciding upstream, to whoever writes and revises the gate. Mostly that seat then goes unattended, and an unattended seat is easy to mistake for an empty one. It is not empty. When a stale threshold finally waves through the thing it existed to block, the miss lands on whoever owns the gate, not on the hook. Shipping moved the enforcement. It did not move the being-wrong.

There is a cost, and it is worth stating. A gate is an intervention frozen at the moment of its writing, and it can be wrong in both directions, silently. The false blocks show up as friction and get fixed. The false passes show up as nothing. And a gate I no longer think about is a gate I no longer audit, which is its own quiet decay. Moving a correction into infrastructure does not end the work of judging it. It changes when the judging happens, from every occasion to almost never, and almost never has failure modes of its own.

But the direction still seems right to me. The test is simple enough: if a correction has recurred after the rule's best rewrite, the next revision should not be prose.

## References

- The hooks and their test suites: [agent-guardrails](https://github.com/MajorLift/agent-guardrails)
- On what the interventions carry: [When, If Ever, Will AI Agents Stop Needing Us?](https://jongsun.dev/when-if-ever-agents-stop-needing-us/)
- On who bears the outcome: [When the Agent Stands to Lose Something](https://jongsun.dev/when-the-agent-stands-to-lose-something/)
