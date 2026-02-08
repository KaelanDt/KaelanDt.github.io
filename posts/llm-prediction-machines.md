---
layout: post
title: LLMs are prediction machines
---

## LLMs are prediction machines

In 2023, I listened to a [podcast where Ilya Sutskever said something](https://www.youtube.com/watch?v=Yf1o0TQzry8) that stayed with me, and that I still think about on most days:

```
To predict the next word is to understand the whole world around it.
```

In the short-term, that sentence had the effect of convincing me that indeed, next-token prediction could be much more than next-token prediction, in the sense that a model can in principle become good at maths with enough training data, even if not math-heavy. Scaling works, meaning that if you follow the recipe, and increase the number of parameters and the size of the dataset you will get better performance accross basically all domains.

Fast-forward to 2026, today, where coding agents are all the rage and the release of OpenClawd convinced the Linkedin influencers that AGI is here. We all had some time for these thoughts to distill, and to see the limitations of these systems. For me, the main one can be clarified by going back to David Deutsch's Fabric of Reality, where he attempts to define the distinction between prediction and understanding.

Now I won’t attempt to give a rigorous definition of “understanding” or “explanation”, that is a never-ending debate and it's just too difficult to narrowly define them. Instead, I mean the sort of activity that leads to new scientific frameworks: proposing new entities, mechanisms, or laws that reorganize a field and make testable predictions, that examine counterfactuals, that invent thought experiments, rather than merely accelerating search inside existing predictions.

Deutsch imagines a machine, the prediction machine, that can predict the outcome of any physics experiment. Then he asks the question of how useful such a machine would be to a physicist. Think about it: if Einstein had a prediction machine, how would that help his work?

The obvious thing is that it would speed it up. He wouldn't have had to send people out to accurately measure Mercury's movement to prove general relativity worked, and a lot of things throughout his career would have been experimentally corroborated way faster. However, he would have still gotten the Nobel prize. Because he was the one asking the questions, and coming up with new explanations of things. In fact, the central piece here is that a prediction machine does not explain anything. It receives a question, runs the experiment or the simulation, and outputs the answer. It has no intelligence in the human sense, and it does not create any knowledge in the Deutschian sense (which requires explanation). To know what question to ask, what experiment to run, you need explanation, because you need to know what would change your explanation for the phenomena you are trying to understand. All these things are foreign to the prediction machine. 

Now take LLMs. From the point of view of scientists these are quite similar to prediction machines: a physicist can use them to help him with a numerical simulation or a calculation, they can help a mathematician in their proof. They also help software engineers write software, but in all these domains, the main limitation outlined above remains true: they don't provide the right questions to ask and the good explanations. For more about the right questions, see [this funny controversy around why the French are overrepresented in Fields medal winners but underrepresented in IMO winners](https://x.com/alz_zyd_/status/2019956661809791393). (Indeed, solving known problems fast is a _very_ different skill than finding new ones!) 

The common counterpoint to this is that if a system is able to predict accurately any sequence you provide to it, eventually it will develop an understanding, for example through the structure of its parameters for neural networks. Let's ask the question to Gemini 3 Pro:

Prompt:
```
What do you think are the biggest problems in modern physics, and how would you solve them?
```

Sparing the details, part of its answer:

```
How I would help solve quantum gravity: I cannot derive a theory of everything on my own, but I can
perform Symbolic Regression and Topology Analysis.

* Exploring String Theory: String theory requires dimensions compacted into complex shapes 
(Calabi-Yau manifolds). There are roughly $10^{500}$ possible shapes.
I can categorize these shapes billions of times faster than a human to find the one that matches
our universe’s particle physics.

* Checking Consistency: I can formally verify complex mathematical proofs in Loop Quantum Gravity
to ensure no logical steps were missed by human theorists.
```

Apart from the fact that Gemini seems to be aware of its own limitations, and that the system is quite complex and unknown with the post-training recipes that are applied, I can't help but think "what a bad answer". I don't know much about the topic, but I know that checking the proofs for loop quantum gravity isn't the best use of anyone's time, even that of an AI. Of course this is just a single example and my prompt wasn't particularly well-thought, but the crux of the problem is very simply shown here: there doesn't seem to be any understanding or explanations that come out of the model, except those that are found online. You also see this with code very often: it's by providing the explanations yourself, and re-nudging the model that you eventually get something useful. The out-of-distribution problem is really far from being solved for things that are not easily verifiable, which is tightly related to all this.

Now there are a few companies that are trying to build a full-on AI scientist, and a few papers that have tried to approach the problem. But the issue with this is that it becomes clear that they lack any form of new explanation of new understanding of a problem: they tweak parameters and reproduce a problem. It may be that they are able to find flaws in a theory by running the right experiment by luck; but first of all, that would be incredibly lucky given all the possible experiments in the world for a given domain, and second, that would only be a very tiny part of science. To actually do science a general intelligence would have interpret the result, explain why it failed, and propose an explanation/new theory to solve the problem. Consider the CERN experiment that showed [neutrinos were traveling faster than light](https://en.wikipedia.org/wiki/2011_OPERA_faster-than-light_neutrino_anomaly), which was then retracted. Would it have been possible to get to the root cause of this with prediction machines only? Would the prediction machine not have concluded that this was an anomaly, therefore a new theory was needed? 

I read [this post about code automation](https://blog.alaindichiappari.dev/p/software-engineering-is-back) the other day, that reconciled me with coding assistants: treat them like a weaving machine, or like a crane. They are great tools to accomplish your goals, but nothing more. And I believe anything trained with prediction as the core objective will only ever be that way. We are only making them predict better and become good in verifiable domains where we can reward them, which is also exactly not the case of science. This is in fact the crux of supervised learning: the model is shown a label, and it has to predict, and however much training data you provide them, that's only what they will do. Reinforcement learning is suffers from the same problem, where the model is rewarded if it achieved the right outcome, but not how (it could still have made plenty of mistakes in its reasoning trace, for example, demonstrating a lack of understanding).

So I'll make a prediction, and we'll see if it ages well: _No system which was pretrained via next-token prediction will ever make a scientific discovery without human intervention_. They will only ever assist humans or other forms of general intelligence. 

