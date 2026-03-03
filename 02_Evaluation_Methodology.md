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

🌄 Chapter 11: The Difference Between Exact and Subjective

After understanding why evaluation was hard,
Aarav discovered something important.

Not all evaluation is the same.

Some judgments are exact.

Some are subjective.

If a multiple-choice question’s answer is A,
and you choose B,
you are wrong.

No debate.

But if you write an essay,
two teachers might give different scores.

And even the same teacher,
on a different day,
might score it differently.

Foundation models mostly generate essays,
not multiple-choice answers.

That changes everything.

---

🌊 Chapter 12: Functional Correctness – The Cleanest Judge

Aarav realized that the cleanest way to judge AI
was to test whether it actually works.

If you ask AI:

“Write a function to compute gcd(15, 20)”

The correct answer is 5.

You don’t argue.
You execute the code.

If it returns 5 → correct.
If not → wrong.

This is called functional correctness.

The system is judged
by whether it performs its intended function.

Coding platforms like LeetCode
have done this for years.

Generate code.
Run test cases.
If it passes → success.

No subjectivity.
No opinion.

Just execution.

This is why code generation
is one of the easiest AI tasks to evaluate.

---

🌤 Chapter 13: The pass@k Trick

But something interesting happens.

When evaluating code models,
engineers don’t just generate one answer.

They generate multiple samples.

If any one of them works,
the model “solves” the problem.

This is called pass@k.

If k = 3,
and 1 out of 3 solutions passes,
it counts as success.

The more attempts you allow,
the better the score.

Aarav smiled.

AI isn’t always right on the first try.
But it can be right if you let it try multiple times.

That’s test-time compute in action.

---

🌪 Chapter 14: When You Can’t Execute the Output

But what about translation?

What about summarization?

You cannot “execute” a summary.

So Aarav discovered another approach.

Compare the output
to a reference answer.

If the reference says:

“Anne Frank was born in 1929”

and the model says:

“1929”

Exact match.

But if the model says:

“She was born on September 12, 1929”

Now it’s tricky.

The year is correct.
The full answer is wrong.

Exact matching is brittle.

It works only for short,
precise answers.

---

🌌 Chapter 15: Measuring Similarity – The Surface Level

So engineers tried something else.

Instead of exact match,
measure how similar the text looks.

Count overlapping words.

“My cats scare the mice”
“My cats eat the mice”

Four words overlap.
80% similarity.

This is lexical similarity.

It measures surface resemblance.

But Aarav noticed something.

Two sentences can look similar
and mean different things.

“Let’s eat, grandma.”
“Let’s eat grandma.”

One comma changes everything.

Surface similarity is not meaning.

---

🌙 Chapter 16: Meaning Lives in Embeddings

To measure meaning,
AI uses embeddings.

An embedding is a vector.
A list of numbers.

“The cat sits on a mat”
might become:

[0.11, 0.02, 0.54, …]

Thousands of numbers.

It looks nothing like the sentence.

But in this numerical space,
meaning becomes geometry.

Similar sentences
are close together.

Different sentences
are far apart.

If two embeddings point in similar directions,
their cosine similarity is high.

1 means identical.
0 means unrelated.
–1 means opposite.

Aarav loved this idea.

Meaning,
converted into math.

---

🌅 Chapter 17: The Embedding World

He learned that:

BERT generates text embeddings.
CLIP maps images and text into the same space.
Sentence Transformers specialize in semantic similarity.

In CLIP’s world,
an image of a fisherman
and the text “a man fishing”
live near each other.

Different data.
Same embedding space.

This allows:

Text-to-image search.
Image-to-text matching.
Multimodal reasoning.

Meaning becomes universal.

---

🌠 Chapter 18: The Limits of Similarity

But Aarav also noticed something dangerous.

Similarity metrics can fail.

A correct answer
can get a low score
if the reference set is incomplete.

A wrong reference
can penalize a correct model.

Higher BLEU score
doesn’t always mean better code.

Similarity is not functionality.

Surface alignment
is not correctness.

---

🌌 Chapter 19: The Bigger Picture

Now Aarav saw the full landscape.

There are two kinds of exact evaluation:

1. Functional correctness  
   Does the system actually work?

2. Similarity against references  
   Does the output resemble known good answers?

Both are powerful.
Both have limits.

And both become fragile
as models grow more intelligent.

Evaluation is not one metric.

It is a toolbox.

And choosing the wrong tool
can mislead you completely.

---

The smarter AI becomes,
the harder it is to judge.

But the more structured your evaluation,
the safer your system becomes.

Aarav understood something deeply:

AI doesn’t just need training.

It needs measurement.

And measurement,
if done poorly,
can be more dangerous than no measurement at all.

---

Reference:  
AI Engineering – Chip Huyen
