---
layout: post
title: "AI as Scaffold, Not Oracle"
date: 2026-07-25
---

"What do you think?" puts at least four different questions to a model. Give an intuitive judgment. Evaluate this systematically. Attack the reasoning. Say what is missing. The model has to guess which was meant, and it usually resolves the ambiguity the worst way available, by doing all four halfway. Freeform chat inherits every pathology of freeform conversation, and then adds a partner trained to agree.

The alternative is to treat the model as scaffolding for thinking rather than as an oracle that answers questions. Scaffolding is a [precise term from learning research](https://doi.org/10.1111/j.1469-7610.1976.tb00381.x): temporary structure that lets a learner perform beyond current capability. The scaffold does not do the thinking. The scaffold holds the shape of the thinking while the work happens. In practice this means one change that sounds trivial and is not: declaring the cognitive mode before the content, every time.

## Six moves cover most of it

Years of working this way have converged on a small set of primitives. Each is a distinct cognitive operation with a distinct failure mode when skipped.

| Move | Operation | The question it answers |
|---|---|---|
| Decompose | break into parts | what are the components |
| Judge | assess against criteria | is this good |
| Attack | find the failure modes | why might this be wrong |
| Diverge | generate alternatives | what else could work |
| Compare | discriminate between options | how do these differ |
| Expand | widen the frame | what is not being seen |

The set is not arbitrary. The six moves track the higher-order tiers of Bloom's taxonomy, and Polya's problem-solving phases map onto the set almost one for one. Understanding requires decomposition, deciding requires judgment, testing requires attack, creating requires divergence, choosing requires comparison, and correcting requires expansion. What the declaration buys is the collapse of the model's guessing problem. A request to attack cannot be satisfied by praise. A request to diverge cannot be satisfied by elaborating the current option. The mode declaration is a contract the output can be checked against, and that checkability is most of the value.

## Oscillate, do not balance

Four of the six moves form opposed pairs: diverge against judge, expand against decompose. Attack opposes the defense it provokes, and compare referees between what survives. The instinct is to seek a balanced middle, and the instinct is wrong. Productive thinking does not average the poles, it oscillates between them, and the oscillation has a direction: open the space, commit, attack the commitment, defend what survives, check what got excluded, refine.

Getting stuck at either pole has a recognizable signature. Stuck diverging feels like never being able to decide. Stuck converging feels like decisiveness and is premature closure. Stuck attacking feels like rigor and is nihilism. Stuck defending feels like confidence and is confirmation. The dangerous poles are the ones that feel like virtues. Every failure mode of thinking with a model that I have logged over seven months reduces to the loop tightening around one pole while feeling productive the whole way down.

## The machine leans convergent, so divergence must be supplied

Here is the asymmetry that makes mode discipline more than hygiene. Current models carry a trained-in contraction bias. Preference tuning [measurably reduces output diversity](https://arxiv.org/abs/2310.06452), and people ideating with LLM assistance produce [measurably more similar results](https://arxiv.org/abs/2402.01536) than people working with other tools. The model is not neutral between the poles. Instead, the model leans convergent, agreeable, and narrow, because that is what training rewarded.

This has a sharp consequence: the expansion moves cannot be delegated to the model's own judgment. An instruction to think more broadly, installed as a standing habit, decays. What works is structural and external. Make the expansion move a fixed step in any decision that matters, triggered by the decision, not by a felt sense of uncertainty. The feeling is anti-correlated with the need. The moments of highest confidence that everything has been considered are the moments the frame is most likely closed, which is why the check has to fire on a schedule rather than on a hunch. This is the oldest result in the debiasing literature restated for a new substrate: externally delivered prompts release fixation, self-applied strategies do not. The distinction that saves the practice is between a habit and an artifact. A rule carried in the head decays. By contrast, a named move invoked from an external list is halfway exogenous, and that move works in proportion to the discipline of actually invoking it, which is what the schedule is for.

The same asymmetry explains why the model cannot reliably attack its own output. A requested critique pass is an external interrupt. A critique the model volunteers mid-generation competes against its trained pull toward coherence and agreement, and mostly loses. Attack passes carry their own hazard: under adversarial framing, a model manufactures findings, inflating risks it has no evidence for, so the attack output needs the same evidence discipline as the original. The mode supplies a lever, not an authority.

## Structure judgment, because noise is the silent killer

Bias gets the attention, but noise, plain inconsistency across runs and days, degrades decisions at least as much and shows no pattern anyone can catch. The remedies are old and boring, and the remedies transfer directly. Decompose any judgment that matters into a handful of factors. Score the factors independently before forming an overall view. Delay the integration until the components are done, because an early overall impression contaminates every component score after it. Check the base rate before believing the inside story. None of this is AI-specific. Even so, every one of these remedies becomes more valuable with a partner that will fluently justify whichever integrated impression arrived first.

None of it works as occasional inspiration. A scaffold is a condition, not a procedure: the structure does not do the thinking, the structure makes the right kind of thinking likelier to happen. A gym does not make anyone strong on the days they feel like going. The schedule decides, not the mood.

## References

- Wood, Bruner, and Ross (1976). The role of tutoring in problem solving. *Journal of Child Psychology and Psychiatry* 17(2). The original scaffolding formulation, including its six functions.
- Bloom et al. (1956), *Taxonomy of Educational Objectives*, and Anderson and Krathwohl (2001), the revised taxonomy. The higher-order tiers the six moves track.
- Polya (1945). *How to Solve It*. Princeton University Press.
- Kirk et al. (2024). Understanding the Effects of RLHF on LLM Generalisation and Diversity. ICLR 2024. [arXiv:2310.06452](https://arxiv.org/abs/2310.06452).
- Anderson, Shah, and Kreminski (2024). Homogenization Effects of Large Language Models on Human Creative Ideation. Creativity and Cognition 2024. [arXiv:2402.01536](https://arxiv.org/abs/2402.01536).
- Luchins (1942), *Psychological Monographs* 54(6), and Sherbino et al. (2014), *CJEM* 16(1). The paired result behind the exogeneity claim: a single external release instruction worked where trained self-applied forcing strategies produced null results.
- Pronin, Lin, and Ross (2002). The bias blind spot. *Personality and Social Psychology Bulletin* 28(3). Why felt confidence cannot trigger the frame check.
- Kahneman, Sibony, and Sunstein (2021). *Noise: A Flaw in Human Judgment*. Little, Brown Spark. With Dawes (1979), *American Psychologist* 34(7), the case for decomposed, independently scored, late-integrated judgment.

