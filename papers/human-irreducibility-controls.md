---
layout: default
title: "What Can Be Established About Human Irreducibility: Levels, Instruments, and Their Controls"
permalink: /papers/human-irreducibility-controls/
citation:
  title: "What Can Be Established About Human Irreducibility: Levels, Instruments, and Their Controls"
  author: "Suh, Jongsun"
  date: "2026/08/06"
  doi: "10.5281/zenodo.21822225"
---

<article>
<h1>What Can Be Established About Human Irreducibility: Levels, Instruments, and Their Controls</h1>
<p class="post-meta">Jongsun Suh · Working preprint, 2026 · companions: <a href="{{ '/papers/epistemic-content-taxonomy/' | relative_url }}">the taxonomy and its measurement</a> · <a href="{{ '/papers/grounds-frames-standing/' | relative_url }}">what the inventory entails about durability</a></p>

<p>
A measurement is worth the control that could have killed it. That is not what the literature on human-AI oversight currently practises, where the instruments in use are mostly classifiers scored against held-out labels drawn from the same annotation pass that trained them. Twenty instruments built on one practitioner's record of work with LLM coding agents were held to the standard, and eighteen did not survive it. One survived intact, and one stands as a method whose headline contrast is unestablished. Each was run before the control that could kill it was built.
</p>

<p>
Underneath the catalogue the paper argues one claim: any measurement of human oversight is a measurement of a dyad, and the filters that decide what a human ever gets to intervene on sit upstream of the corpus, where no amount of re-coding reaches them. An observed rate is the product of how often the agent creates the occasion and how often the practitioner takes it. That is why the controls are necessary rather than fastidious.
</p>

<p>
An irreducibility claim is a family of claims rather than one, and its members differ in what would absorb them. The six levels run from what a model failed to supply in a session as run, through what it fails to prefer when the answer is placed in front of it, to what cannot be self-conferred at any capability, and each of the five levels above the observational floor names its own absorber: more or better sampling, preference modelling on a particular principal, the domain's verifier availability, externalisation, and at the last level no capability at all but an institutional event. Stating which level a result reaches is what keeps a deployment observation from being read as a limit in principle.
</p>

<p>
Level two is the first level at which such a claim survives free generation, and it is measured on the fifth attempt. Across 38 decision points, ten options at each and three raters per point, a model handed every candidate rates Anthropic-generated proposals at 3.83 of 5 and the human's actual move at 2.33, with a same-register decoy at 1.33 showing the gap is not a penalty on human phrasing. Raters from two other vendors, judging text neither produced, widen the gap rather than closing it, which is the prediction self-preference would have failed. Nothing above level two is measured anywhere, because the levels above it turn on facts about the domain, about preference formation and about conferral semantics rather than about compute.
</p>

<p>
The controls that did the killing are the reportable part, and four of them carry most of the work. A shortcut baseline asks whether a classifier reading nothing but surface markers already scores what the instrument claims to measure. A floor test mixes in items that are not interventions at all and counts how often the rubric grades them anyway. A splice grades a stretch of work the input could not have caused, which is what separates an effect from a sequence. And a matched comparison arm differs from the treatment arm in the treatment and in nothing else. The intact survivor is a read task, and it earns its place by contrast: asked to forecast a human's next move, blind raters scored at chance while agreeing with each other on 77 percent of items, and asked what that move delivered once shown it, two blind coders sorted the raters' descriptions at Cohen's kappa 0.965.
</p>

<p>
<a href="https://doi.org/10.5281/zenodo.21822225">DOI: 10.5281/zenodo.21822225</a> ·
<a href="https://doi.org/10.5281/zenodo.21966986">v0.17</a>
</p>

<p>Every rater in this catalogue is a language model instance rather than a person, and no human
second-rater run has been completed, so an agreement figure here bounds how consistently a model
panel applies a rubric rather than how well that rubric survives an independent human reader.</p>

<p>This is the instruments-and-controls paper of the three drawn from the same corpus. The
taxonomy, its composition and its reliability figures are established in
<a href="{{ '/papers/epistemic-content-taxonomy/' | relative_url }}">the taxonomy paper</a>, and
what the inventory entails about durability is derived in
<a href="{{ '/papers/grounds-frames-standing/' | relative_url }}">its companion</a>. Nothing
catalogued here depends on the taxonomy or its composition being right.</p>
</article>

<p><a href="{{ '/papers/' | relative_url }}">&larr; all papers</a></p>
