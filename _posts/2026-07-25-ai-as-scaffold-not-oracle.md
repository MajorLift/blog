---
layout: post
title: "AI as Scaffold, Not Oracle"
date: 2026-07-25
---

*Declaring the cognitive mode before the content converts an unverifiable exchange with a model into a verifiable one. The declaration, not any particular list of modes, is the scaffold.*

"What do you think?" puts at least four different questions to a model. Give an intuitive judgment. Evaluate this systematically. Attack the reasoning. Say what is missing. The model has to guess which was meant, and it usually resolves the ambiguity the worst way available, by doing all four halfway. Freeform chat inherits every pathology of freeform conversation, and then adds a partner trained to agree.

The fix sounds trivial and is not: declare the cognitive mode before the content, every time. Not "what do you think of this design" but "attack this design". Not "thoughts on these options" but "compare these options on cost of reversal".

## The mode is checkable, the answer is not

Specificity about content buys nothing checkable. The question was asked because the answer was unknown, so no amount of detail in the prompt lets the asker grade the response. Specificity about mode is a different kind of claim. A declared mode constrains the shape of an acceptable response, and shape is verifiable by a reader who does not know the content. I cannot tell whether the model's answer is right. I can always tell whether the output attacked or praised, generated alternatives or elaborated the current one. A request to attack cannot be satisfied by agreement. The declaration is a contract, and checking the contract requires knowing less than the model knows. That condition is the one that matters, because the oracle pattern is dangerous exactly where the asker cannot grade the answer.

Scaffolding is the accurate name for a structure like this, and the term is [precise in learning research](https://doi.org/10.1111/j.1469-7610.1976.tb00381.x): temporary structure that lets a learner perform beyond current capability. The scaffold does not do the thinking. The scaffold holds the shape of the thinking while the work happens. A mode declaration holds exactly one shape at a time.

## Any short list of named modes serves

In practice I declare from a list of six.

| Mode | Operation | The question it answers |
|---|---|---|
| Decompose | break into parts | what are the components |
| Judge | assess against criteria | is this good |
| Attack | find the failure modes | why might this be wrong |
| Diverge | generate alternatives | what else could work within the frame |
| Compare | discriminate between options | how do these differ |
| Expand | widen the frame | is the frame itself missing options |

The list is inherited, not discovered. The higher-order tiers of Bloom's taxonomy contain it, and Polya's problem-solving phases map onto the set almost one for one. Any set with the same coverage would serve, provided the modes are few, named, and exclusive enough that an output can be checked against the one declared. One distinction inside the set does need stating, because the short glosses run close together: diverge generates more options inside the current frame, while expand asks whether the frame is admitting the right options at all.

## Oscillate, do not balance

Four of the six modes form opposed pairs: diverge against judge, expand against decompose. Attack opposes the defense it provokes, and compare referees between what survives. The instinct is to seek a balanced middle, and the instinct is wrong. Productive thinking does not average the poles, it oscillates between them, and the oscillation has a direction: open the space, commit, attack the commitment, defend what survives, check what got excluded, refine.

Getting stuck at either pole has a recognizable signature. Stuck diverging feels like never being able to decide. Stuck converging feels like decisiveness and is premature closure. Stuck attacking feels like rigor and is nihilism. Stuck defending feels like confidence and is confirmation. The dangerous poles are the ones that feel like virtues. Most of the failures I have logged while thinking with a model reduce to the loop tightening around one pole while feeling productive the whole way down. The log behind that claim has narrow scope: one practitioner, roughly one session in fifteen covered across seven months, and debriefs written only where something needed fixing. Counts from a record like that are not rates, so the pattern stands as an observation for better data to test, not a result.

## The machine leans convergent, so divergence must be supplied

Here is the asymmetry that makes mode discipline more than hygiene. Current models carry a trained-in contraction bias. Preference tuning [measurably reduces output diversity](https://arxiv.org/abs/2310.06452), and people ideating with LLM assistance produce [measurably more similar results](https://arxiv.org/abs/2402.01536) than people working with other tools. The model is not neutral between the poles. Instead, the model leans convergent, agreeable, and narrow, because that is what training rewarded.

This has a sharp consequence: the expansion modes cannot be delegated to the model's own judgment. An instruction to think more broadly, installed as a standing habit, decays. What works is structural and external. Make the expansion mode a fixed step in any decision that matters, triggered by the decision, not by a felt sense of uncertainty. The feeling disqualifies itself as a trigger, because people fail to detect bias in their own judgment even while detecting the same bias in others. No study I know of measures felt completeness against actual completeness, which is the quantity a confidence trigger would need. Absent that measurement the feeling is unvalidated rather than shown useless, and an unvalidated trigger is not one to build a practice on. The check has to fire on a schedule rather than on a hunch.

The oldest debiasing results say the same about who delivers the prompt. Externally delivered release instructions break fixation, and trained self-applied strategies produce null results. The distinction the practice leans on is between a habit and an artifact. A rule carried in the head decays, while a named mode invoked from an external list is at least halfway exogenous. From my own log, mid-investigation: "keep going /falsify with cross-ref data | /vet". Two named checks, an attack pass and a source audit, invoked by handle, with the list the checks come from living outside the head that invokes them. But invoking that list is still self-applied, and the cited studies found null results for self-applied strategies, so whether the external artifact escapes the null result is exactly what my evidence cannot settle. The far end of the spectrum is a check that fires without being invoked at all, which is the subject of [Gates, Not Reminders](https://jongsun.dev/gates-not-reminders/).

The same asymmetry explains why the model cannot reliably attack its own output. A requested critique pass is an external interrupt. A critique the model volunteers mid-generation competes against its trained pull toward coherence and agreement, and mostly loses. Attack passes carry their own hazard: under adversarial framing, a model manufactures findings, inflating risks it has no evidence for, so the attack output needs the same evidence discipline as the original. The mode supplies a lever, not an authority.

## Decomposed judgment matters more with a fluent partner

Judgment calls need one further piece of structure, because plain inconsistency across runs and days degrades decisions as much as bias does and shows no pattern anyone can catch. The remedies are old: decompose the judgment into factors, score the factors independently, integrate late, and check the base rate before believing the inside story. None of that is AI-specific. Every one of those remedies matters more, though, with a partner that will fluently justify whichever integrated impression arrived first.

None of it works as occasional inspiration. A scaffold is a condition, not a procedure: the structure does not do the thinking, the structure makes the right kind of thinking likelier to happen. A gym does not make anyone strong on the days they feel like going. The schedule decides, not the mood.

## References

- Wood, Bruner, and Ross (1976). The role of tutoring in problem solving. *Journal of Child Psychology and Psychiatry* 17(2). The original scaffolding formulation, including its six functions.
- Bloom et al. (1956), *Taxonomy of Educational Objectives*, and Anderson and Krathwohl (2001), the revised taxonomy. The higher-order tiers the six modes track.
- Polya (1945). *How to Solve It*. Princeton University Press.
- Kirk et al. (2024). Understanding the Effects of RLHF on LLM Generalisation and Diversity. ICLR 2024. [arXiv:2310.06452](https://arxiv.org/abs/2310.06452).
- Anderson, Shah, and Kreminski (2024). Homogenization Effects of Large Language Models on Human Creative Ideation. Creativity and Cognition 2024. [arXiv:2402.01536](https://arxiv.org/abs/2402.01536).
- Luchins (1942), *Psychological Monographs* 54(6), and Sherbino et al. (2014), *CJEM* 16(1). The paired result behind the exogeneity claim: a single external release instruction worked where trained self-applied forcing strategies produced null results.
- Pronin, Lin, and Ross (2002). The bias blind spot. *Personality and Social Psychology Bulletin* 28(3). Bias detected in others goes undetected in the self, so felt confidence cannot trigger the frame check.
- Kahneman, Sibony, and Sunstein (2021). *Noise: A Flaw in Human Judgment*. Little, Brown Spark. With Dawes (1979), *American Psychologist* 34(7), the case for decomposed, independently scored, late-integrated judgment.
