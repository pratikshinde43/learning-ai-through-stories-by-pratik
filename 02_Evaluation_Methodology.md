# The Story of Evaluation  
A Beginner-Friendly Journey into Why Judging AI Is Harder Than Building It

🌅 Chapter 1: Aarav Meets the Overconfident Machine

Aarav was proud.

He had built his first AI application.
It could summarize articles.
Answer questions.
Even generate legal drafts.

It felt powerful.

Until one day,
a user emailed him.

“The AI gave me wrong information.”

Not obviously wrong.
Not gibberish.
Not nonsense.

Confidently wrong.

That’s when Aarav realized something:

Building AI was easier than judging it.

---

🌄 Chapter 2: The Problem With Smart Machines

At first, evaluating AI seemed simple.

If output = correct → good.
If output = wrong → bad.

That works for:
- Spam detection
- Image classification
- Fraud detection

But foundation models don’t give fixed answers.

For one question,
there can be 100 valid responses.

Which one is “correct”?

There is no single ground truth.

And worse —
sometimes the wrong answer sounds perfect.

---

🌤 Chapter 3: The PhD Problem

Aarav read something that changed his perspective:

“It’s easy to tell if a first grader’s math is wrong.
Harder to judge a PhD-level proof.”

AI models are becoming PhD-level.

To evaluate them, you might need:
- Domain expertise
- Fact-checking
- Deep reasoning

Evaluation is no longer a quick check.
It’s investigation.

And investigation takes time.

---

🌊 Chapter 4: The Open-Ended Curse

Traditional machine learning was clean.

Input → Output  
Compare with label → Done.

But foundation models are open-ended.

Ask:
“Summarize this book.”

There are infinite valid summaries.

You cannot create a list of all correct answers.

Evaluation breaks.

Aarav understood:
The open-ended nature of AI makes traditional evaluation useless.

---

🔥 Chapter 5: The Black Box

Aarav wanted to understand why the model failed.

But he couldn’t see:
- Training data
- Architecture details
- Internal reasoning

The model was a black box.

He could only judge it by outputs.

It was like evaluating a student
without knowing what they studied.

---

🌪 Chapter 6: When Benchmarks Stop Working

Aarav learned about benchmarks:
GLUE.
SuperGLUE.
MMLU.

Models beat them quickly.

A benchmark becomes useless
once models get perfect scores.

Evaluation has to evolve.

And it must evolve fast.

---

🌙 Chapter 7: The Temptation of Eyeballing

Some developers said:
“Just eyeball the outputs.”
“Looks good to me.”

But Aarav knew that was dangerous.

Confidence is not correctness.
Fluency is not truth.

Without systematic evaluation,
AI risk can outweigh AI benefit.

---

🌌 Chapter 8: Measuring Uncertainty – The Hidden Math

Before foundation models,
language models were evaluated using:

Entropy.
Cross entropy.
Perplexity.

Aarav simplified it in his mind:

Perplexity answers one question:

“How confused is the model
when predicting the next word?”

Lower perplexity → more confident predictions.
Higher perplexity → more uncertainty.

If a model has perplexity of 3,
it’s like saying:
“I’m choosing among 3 likely options.”

Given vocabularies of 100,000 words,
that’s impressive.

But here’s the twist:

After alignment (RLHF, SFT),
perplexity can increase.

The model gets better at tasks,
but worse at raw prediction.

Evaluation isn’t straightforward.

---

🌅 Chapter 9: The AI Judge

Then Aarav discovered something surprising.

To evaluate AI,
people started using AI.

AI as a judge.

One model generates.
Another scores.

But that creates a new question:

Can AI be trusted to evaluate AI?

The debate had begun.

---

🌠 Chapter 10: The Realization

Aarav finally understood.

Evaluation is not a metric.
It is a system.

You must:
- Identify failure points.
- Design metrics around risks.
- Build evaluation pipelines.
- Iterate continuously.

Because the smarter AI becomes,
the harder it is to judge.

And one day,
AI may become so advanced
that only the brightest humans
can evaluate it.

The challenge isn’t building intelligence.

It’s measuring it.

---

Reference:  
AI Engineering – Chip Huyen
