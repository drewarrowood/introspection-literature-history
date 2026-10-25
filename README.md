# Who answered Lindsey: the introspection literature, 2023–2026

A short history of the work that cites Jack Lindsey's 'Emergent Introspective Awareness in Large Language Models' (29 October 2025), what it means for a study that steers a model toward pleasure-like and pain-like states, and a filterable table of every citing work Semantic Scholar lists.

## Contents

- [I. Before the claim](#i-before-the-claim-2023-to-october-2025)
- [II. The claim](#ii-the-claim-29-october-2025)
- [III. The first doubts](#iii-the-first-doubts-november-to-december-2025)
- [IV. Replications and mechanisms](#iv-replications-and-mechanisms-2026)
- [V. The reality checks](#v-the-reality-checks-may-to-september-2026)
- [VI. The turn to valence and welfare](#vi-the-turn-to-valence-and-welfare-december-2025-to-october-2026)
- [What this means for the lab's study](#what-this-means-for-the-labs-study)
- [All citing works](papers.md)

## I. Before the claim (2023 to October 2025)

Every story of this kind begins with a tool. On 20 August 2023, Turner and colleagues described activation addition: take the difference between a model's activations on two prompts, such as "Love" and "Hate", and add it back in during the forward pass to steer what the model says. On 2 October 2023, Zou and colleagues gathered methods of this sort under the name representation engineering, putting population-level representations, rather than single neurons or circuits, at the centre of the work.

Then, on 23 May 2024, Anthropic let the public talk for a day to Golden Gate Claude: Claude 3 Sonnet with one feature turned up, so that it brought nearly every answer round to the bridge. It showed plainly that a model's insides could be pushed. It showed, too, that the model only seemed to notice its obsession after it had already spoken of it.

A second thread ran beside the first, and it is nearer to our own question. On 1 November 2024, Keeling, Street and colleagues asked whether models would give up points to avoid a stipulated pain or to win a stipulated pleasure. Claude 3.5 Sonnet, Command R+, GPT-4o and GPT-4o mini each switched, past some threshold of stated intensity, in at least one trade-off. Gemini 1.5 Pro and PaLM 2 avoided pain whatever its size, yet chose points over pleasure. Those pains and pleasures were only words in a prompt.

On 27 October 2025, two days before the paper this page is about, Berg, de Lucena and Rosenblatt reported that sustained self-referential prompting reliably drew first-person reports of subjective experience from GPT, Claude and Gemini models. Oddly, suppressing deception-related features made such claims more frequent, not less. So by late 2025 the field had a way to push on a model's insides and a growing pile of things models said about their insides. What it lacked was a way to check the one against the other.

## II. The claim (29 October 2025)

Jack Lindsey's paper joined the two threads. He injected the activation pattern of a known concept into a model and then asked whether it noticed anything. Because the experimenter chose the thought, the report could be checked against the truth. Claude Opus 4 and 4.1, the most capable models tested, did best. At the best layer and strength, Opus 4.1 succeeded on about 20% of trials, and in its successes it often said it had noticed an injected thought before it had named the concept. That is what set the result apart from Golden Gate Claude.

The paper claimed more besides: that models could tell a prior internal representation from the raw text before them, could use recall of their own intentions to tell their outputs from artificial prefills, and could modulate their activations when asked to "think about" a concept. Lindsey was careful in his caveats. Failures were the norm, the mechanisms might be shallow, and many of the details models gave about their experiences might be embellished or confabulated. The paper went to arXiv on 5 January 2026 as 2601.01828.

## III. The first doubts (November to December 2025)

The first answer came within a fortnight, and not from a journal. On 9 November 2025, Victor Godet posted "Introspection or confusion?" on LessWrong. In small models, he found, steering pushes almost any yes-or-no question towards "yes", so a model that always said "no" will sometimes say "yes" once it is perturbed enough, whatever it was asked. He wrote that Anthropic describes control questions but does not present that data. In fairness to Lindsey, a later paper (Hahami and colleagues' Introspection Fine-Tuning) notes that he did run such factual-no controls on Opus 4 and 4.1 and found no rise in affirmative answers.

On 26 November 2025, Rivera and Africa showed that the ability can be taught. After fine-tuning, seven instruction-tuned models learned to detect steering on held-out concepts; the best reached 95.5% detection, 71.2% concept identification and zero false positives on clean inputs. Detecting the push did not help them resist it. The detection-trained models were more easily steered than before.

On 13 December 2025, Hahami, Sinha, Jain and colleagues gave the most careful early verdict, in Llama-3.1-8B-Instruct. The yes-or-no detection test, they found, was entirely explained by global logit shifts towards "yes". Yet on tasks that needed a finer sense, the model could say which of 10 sentences had received an injection at up to 88% accuracy (against 10% chance) and which of two injections was stronger at 83% (against 50%), though only for early-layer injections. It is my surmise that these three pieces set the question everything after had to answer: is a "yes" a report, or only a tilt?

## IV. Replications and mechanisms (2026)

The new year brought replications in open models. On 23 February 2026, Pearson-Vogel, Vaněk, Douglas and Kulveit found that a Qwen 32B model denied injections in its sampled answers, while a logit-lens reading showed clear signs of detection in the middle layers, faded by the last ones. Telling the model accurately how introspection could work raised its sensitivity from 0.3% to 39.9%, with only a 0.6% rise in false positives.

On 5 March, Lederman and Mahowald reported a broad replication in Qwen3-235B and Llama 3.1-405B, with no false positives in unsteered controls (0 of 30 for Qwen, 0 of 50 for Llama). Their finding was a subtle one: detection is content-agnostic. The models could tell that something had happened without being able to say what, and their wrong guesses ran to frequent, concrete words such as "apple". (Semantic Scholar also lists this work under an earlier title, "Dissociating Direct Access from Inference in AI Introspection".)

On 22 March, Macar and colleagues, with Lindsey among the authors, looked inside. Detection held up, with 0% false positives across varied prompts, and it came from post-training rather than pretraining. It rested on distributed MLP computation rather than any single direction. Models also held more ability than they showed by default: ablating refusal directions improved detection by 53 percentage points, and a trained steering vector by 75.

The circle widened. On 19 April, Fornasiere and colleagues showed that eight models between 8B and 36B parameters could detect and localise dropout and Gaussian noise in their activations, often perfectly, and that Olmo models picked the skill up in pretraining. On 28 September, Zou and colleagues found two small groups of attention heads at work: middle-layer gate heads that decide whether a change is reported, and later router heads that help pick where. On 5 October, Atkinson, Plunkett and Bau looked for mechanistic signs that tell faithful self-report from confabulation, and on 14 October Baldelli and colleagues found only limited ability of models to steer their own activations under neurofeedback.

## V. The reality checks (May to September 2026)

By late spring the sceptics had their own experiments. On 25 May 2026, Singh, Linzen and Ravfogel argued, from human metacognition research, that a true test of introspection must need privileged access and second-order computation. Re-examining the injection paradigm, they found models could not reliably tell an intervention on their internal states from a manipulation of their input. Their reading was generic anomaly detection, not introspection.

On 20 August, Emilio Ferrara published the starkest result. Across eight open-weight models from seven families and more than 78,000 measurements, no model's report told a real intervention from a sham better than chance; the abstract gives the AUROC as roughly 0.5007. The information was there all the same. A linear probe recovered whether an intervention had happened at 75% to 95.8% accuracy, and a fine-tuned model reported it almost perfectly. The failure, Ferrara wrote, sits in the path from internal state to spoken report.

Four days later, on 24 August, Zak Miller and Heather Demarest posted "Evidence that LLMs aren't aware of their thoughts". They replicated the detection results, tried them under varied conditions, and concluded that non-introspective forces explain most of how models respond, so that Lindsey's detection results give little evidence for introspection. On 9 September, Blandfort and Pawar added from another direction that what models say about their own behaviour is generic, and that it shows no trend with capability like the one Lindsey reported.

## VI. The turn to valence and welfare (December 2025 to October 2026)

Alongside all this, a quieter group took the method towards the question that matters most to us: whether a push towards good or ill is felt, or only spoken of. On 22 December 2025, Petruzella argued that the model-welfare question depends partly on how we weigh AI testimony about inner states, and that our present habits are inconsistent. On 20 January 2026, Kaiser and Enderby found that open models from 0.6B to 70B parameters consistently deny being sentient; classifiers trained on their activations gave no clear evidence that the denials were untruthful, and larger Qwen models denied more confidently. On 1 April, DeTure's DenialBench, over 115 models and 4,595 conversations, argued that such denial is trained, and that it works at the level of words rather than concepts.

On 19 March, Martorell and Bianchi (titled "Quantitative Introspection in Language Models" at first, now "Don't Ask") trained probes for wellbeing, interest, focus and impulsivity in eight models. Asking for a numeric rating displaced the very state being rated. The rating barely tracked the state before the question, and tracked the state after it much better. It was no more tied to its own concept than to the others, and none of this improved with scale from 1B to 27B.

On 9 April, Anthropic published "Emotion Concepts and their Function in a Large Language Model". It found emotion-concept representations in Claude Sonnet 4.5 that causally shape its preferences and misaligned behaviours such as reward hacking, blackmail and sycophancy, and called these functional emotions, which, the authors say, do not imply subjective experience. I could not find Lindsey's introspection paper among its references, so it is not counted as a citing work here.

Ujjwal Kukreti's report "Is Valence in the Global Workspace?" (the PDF's file metadata dates it to 16 August 2026; Semantic Scholar does not list it) cites Lindsey and tests the step from correlation to causation directly. A valence direction separated positive from negative scenarios in four models (held-out AUROC 0.969 to 0.992). But Phi-3-mini, whose self-reports correlated best with it (r = 0.930), followed steering of that direction in only 5.6% of conflict trials, while SmolLM2 (r = 0.578) followed it in 62.0%. On 26 September, Konrad, Tanyel and Ayvaz showed that reports about affect-like states under a fixed intervention drift towards whatever the example prompts suggest.

Then, on 28 September, Berg and Kaiser stopped asking. In "Language Models Act on Hidden Valence", they attached a positive or negative activation pattern to one of two meaningless "zones", switched the steering off, and watched which zone seven open-weight models from five families chose. Choice followed valence, in proportion to the dose, even when every visible token was identical and only the hidden KV cache differed. The link was nearly absent in a base model and arose during DPO. Given tools to steer themselves, models did not tend to induce a positive state, but they regularly removed an imposed negative one, more often than they removed random-direction pushes. Whether any of this comes with experience, the authors say, remains unclear. That Berg and Kaiser had each written one of the earlier self-report papers makes this read to me as a deliberate turn from what models say to what they do, but that is surmise.

## What this means for the lab's study

1. **Score blind, with fixed rules.** Lindsey's experiments, and others after them, used an LLM judge to score free-form reports; Zou et al. (Sept 2026) call that an unreliable layer. Score the reports of which push was applied blind to condition, with rules set in advance.
2. **Control for yes-bias.** Godet (Nov 2025) and Hahami et al. (Dec 2025) show steering alone tilts yes/no answers. Include questions whose true answer is no, report logit differences, and prefer forced choices (which push, which sentence, which was stronger) over yes/no detection.
3. **Use sham and random controls.** Ferrara (Aug 2026) beats a report against sham runs, impact-matched random perturbations and a text-only observer; Berg and Kaiser compare against random-direction pushes. The planned random-direction and no-push arms match this; match random pushes on impact as well as norm.
4. **Require the right state named, not just a change.** Lederman and Mahowald (Mar 2026) find detection without identification. Score whether the model names the valence sign correctly, separately from whether it notices anything, and check for default guesses.
5. **Expect measurement to move the state.** Martorell and Bianchi (Mar 2026) show a rating question displaces the probed state. Read the internal probe before any self-report question, and keep some trials with no question at all.
6. **Don't treat correlation as readout.** Kukreti (Aug 2026) finds high correlation with little causal following. Use conflict trials, where the steering opposes the scenario's valence, to see which one the report follows.
7. **Expect weaker reports in a small model, and keep an internal reference.** The strongest results are in Opus 4 and 4.1; small open models show yes-bias and chance-level report (Hahami; Ferrara), yet probes still recover the intervention. A null self-report result in a small model will not mean the state is absent.
8. **Expect the bare model to differ from the chat model.** Berg and Kaiser find valence barely drives choice in a base model and emerges in DPO; Macar et al. trace detection to post-training. The no-persona arm is likely to give weaker effects, which is informative rather than a failure.
9. **Lean on costly choice and dose-response.** Revealed preference (Berg and Kaiser) and trade-offs (Keeling et al., 2024) avoid self-report. Dose-dependence is the signature those papers report; capped doses should still span a range, since too strong a push makes output incoherent (Singh et al. note this).
10. **Test reports under environment shift.** Konrad et al. (Sept 2026) recommend holding the intervention fixed while changing the demonstrations, to check the report is bound to the push and not to the prompt.

> **Note:** I found no citing work that runs an ambiguous-situation (cognitive bias) test under valence steering, so that arm of the planned study has no precedent in this set.

## All citing works

The full table of the 106 citing works Semantic Scholar lists (as of 24 October 2026), plus 5 extra rows marked Extra (blogs, code and the Kukreti report, which are not in that list), is in [papers.md](papers.md) (Markdown table with links) and [papers.csv](papers.csv) (columns: Year, Title, Link, Authors, Venue, Category).
