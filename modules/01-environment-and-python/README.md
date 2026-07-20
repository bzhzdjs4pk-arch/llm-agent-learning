# Module 1 — Environment, Python, and the LLM Landscape

> Week 1 · 4–6 hours · Goal: understand the end-to-end LLM workflow and prepare a reproducible workspace for later modules.

## Outcomes

By the end of this week, you should be able to:

- explain language modeling as next-token prediction;
- sketch the path from text to tokens, Transformer logits, sampling, and generated text;
- distinguish pretraining, supervised fine-tuning, and preference/reinforcement learning;
- run Python in an isolated environment and make a small PyTorch tensor calculation;
- navigate the official codebases used later in the curriculum.

## Before you start

CS336 is an implementation-heavy graduate course. In Week 1, use its first lecture for orientation rather than trying to finish its assignment. Stanford lists Python, deep learning, systems, calculus, linear algebra, probability, and machine learning as prerequisites.

Choose one environment path:

- **Fastest:** [Google Colab](https://colab.research.google.com/) — no local setup required.
- **Local:** [Python](https://www.python.org/downloads/), [uv](https://docs.astral.sh/uv/getting-started/installation/), [Git](https://git-scm.com/downloads), and [VS Code](https://code.visualstudio.com/download).

## Weekly plan

| Session | Bedtime audio (screen off after starting) | Daytime follow-up | Time |
| --- | --- | --- | ---: |
| Day 1 | Karpathy: *State of GPT* | Draw the LLM lifecycle from memory | 45–60 min |
| Day 2 | Karpathy: *Let's build GPT* — first pass | Run the companion notebook/code | 60–90 min |
| Day 3 | Stanford CS336 Lecture 1 | Inspect lecture code and Assignment 1 | 60–90 min |
| Day 4 | Hugging Face LLM Course, Chapter 1 | Run one `pipeline()` example | 45–60 min |
| Day 5 | Review or re-listen to a difficult section | Write the checkpoint answers | 30–45 min |

For bedtime listening, queue the resource before turning off the light. Code, diagrams, and terminal work belong in the daytime follow-up.

## Lesson 1.1 — The LLM landscape

### Watch

- [Andrej Karpathy — State of GPT](https://www.youtube.com/watch?v=bZQun8Y4L2A)

Why: this gives a compact map of tokenization, pretraining, fine-tuning, evaluation, and inference.

Listen for:

- how raw text becomes a training signal;
- what changes between pretraining and assistant fine-tuning;
- why model behavior is probabilistic;
- where prompting fits into the stack.

### Produce

Create a one-page sketch containing:

```text
data -> tokenizer -> Transformer pretraining -> base model
     -> fine-tuning/alignment -> assistant model -> inference
```

Do not worry about precise architecture details yet; those belong to later modules.

## Lesson 1.2 — Build GPT once, end to end

### Watch and code

- [Andrej Karpathy — Let's build GPT: from scratch, in code, spelled out](https://www.youtube.com/watch?v=kCc8FmEb1nY)
- [Official companion repository](https://github.com/karpathy/ng-video-lecture)
- [Companion notebook: `gpt.ipynb`](https://github.com/karpathy/ng-video-lecture/blob/master/gpt.ipynb)
- [Compact final implementation: `gpt.py`](https://github.com/karpathy/ng-video-lecture/blob/master/gpt.py)

First pass: watch or listen without pausing to master every line. The goal is to see the complete path: dataset, character tokenizer, batches, attention, Transformer blocks, loss, training, and sampling.

Daytime task:

1. Open `gpt.ipynb` in Colab or locally.
2. Run through the bigram baseline.
3. Print one input batch and its target batch.
4. Write two sentences explaining why each target is the input shifted by one token.

Optional preview for a later training module:

- [Karpathy — build-nanogpt repository](https://github.com/karpathy/build-nanogpt)
- [Main training implementation: `train_gpt2.py`](https://github.com/karpathy/build-nanogpt/blob/master/train_gpt2.py)

## Lesson 1.3 — Stanford CS336 orientation

Use the stable 2026 course hub for current materials and the complete 2025 playlist for recorded lectures.

### Watch and inspect

- [CS336 course website](https://cs336.stanford.edu/)
- [CS336 Spring 2025 YouTube playlist](https://www.youtube.com/playlist?list=PLoROMvodv4rOY23Y0BoGoBGgQ1zmU_MT_)
- [Lecture 1 executable notes/code](https://github.com/stanford-cs336/lectures/blob/main/lecture_01.py)
- [All official lecture materials](https://github.com/stanford-cs336/lectures)
- [Assignment 1: Basics](https://github.com/stanford-cs336/assignment1-basics)

Focus only on:

- what a language model is;
- tokenization and why byte-pair encoding is useful;
- the components students will implement across the course;
- the relationship among model quality, compute, memory, and data.

Do **not** start the full assignment this week. Read its overview and identify where tokenizer, Transformer, loss, and optimizer work will appear in later modules.

## Lesson 1.4 — Use a pretrained Transformer

### Read, watch, and run

- [Hugging Face LLM Course — introduction](https://huggingface.co/learn/llm-course/chapter1/1)
- [Transformers, what can they do?](https://huggingface.co/learn/llm-course/chapter1/3)
- [How do Transformers work?](https://huggingface.co/learn/llm-course/chapter1/4)
- [Official course source repository](https://github.com/huggingface/course)
- [Transformers repository](https://github.com/huggingface/transformers)

Run the first text-generation or classification `pipeline()` example. Record:

- model identifier;
- task;
- input;
- output;
- one surprising or incorrect behavior.

The high-level pipeline is intentionally a black box this week. Later modules will open tokenizer, model, generation, and inference components separately.

## Reading

- [Rich Sutton — The Bitter Lesson](http://www.incompleteideas.net/IncIdeas/BitterLesson.html)
- [PyTorch: Tensors tutorial](https://docs.pytorch.org/tutorials/beginner/basics/tensorqs_tutorial.html)
- [nanoGPT](https://github.com/karpathy/nanoGPT) — skim the repository structure only.
- [llama.cpp](https://github.com/ggml-org/llama.cpp) — find the examples and documentation directories.
- [vLLM](https://github.com/vllm-project/vllm) — read the first section of the README.
- [MLX](https://github.com/ml-explore/mlx) — Apple silicon array framework; skim its examples.

## Mini exercise

Create a short note at `notes/week-01.md` with this template:

```markdown
# Week 1

## What I learned

## What is still unclear

## One experiment and its result

## Questions to revisit

## Review dates
- Day 3:
- Day 14:
- Day 30:
```

Then answer these questions without looking at the resources:

1. What is a token, and why is it not always a word?
2. Why can next-token prediction produce useful general capabilities?
3. What is the difference between pretraining and assistant fine-tuning?
4. What do logits represent before sampling?
5. Where do the tokenizer, Transformer, and sampling algorithm sit in the generation path?

## Completion checklist

- [ ] Watched *State of GPT*.
- [ ] Completed a first pass of *Let's build GPT*.
- [ ] Ran at least the bigram section of the companion notebook.
- [ ] Watched CS336 Lecture 1 and inspected its official code.
- [ ] Ran one Hugging Face pipeline example.
- [ ] Created `notes/week-01.md`.
- [ ] Answered all five checkpoint questions in my own words.
- [ ] Scheduled Day 3, Day 14, and Day 30 reviews.

## Link maintenance

Prefer the official course hub and repositories when a recording moves. Links in this module were checked on 2026-07-20. Report or fix broken links in the same commit that updates the affected lesson.
