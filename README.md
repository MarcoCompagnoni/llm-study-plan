# llm-study-plan

A study plan for large language models and agents, from the ABC to the frontier of research. I write it down before I start, so you can follow it, check it, and tell me what I should not skip.

## How it works

- Twelve modules, in logical order. Each one ends with a **proof**: something that has to run, with numbers.
- A module is done only when its proof runs and I can explain the logic in my own words.
- Progress is the table at the bottom. It starts empty and changes at each stop.
- I post a stop on LinkedIn and X at most every two weeks. If no proof was closed, the post says so, with a zero.
- Code worth showing goes in its own public repository, one per stop.

The shape of the plan follows Jacob Hilton's [Deep Learning Curriculum](https://github.com/jacobhilton/deep_learning_curriculum) and Stanford's [CS336](http://cs336.stanford.edu/).

## The modules

### 0. Setup
- Material: appendix A of Sebastian Raschka's [Build a Large Language Model (From Scratch)](https://github.com/rasbt/LLMs-from-scratch).
- Proof: a Python and PyTorch environment where the first exercise runs.

### 1. The math that papers use
- Material: 3Blue1Brown, [Essence of linear algebra](https://www.3blue1brown.com/lessons/vectors) and [Essence of calculus](https://www.3blue1brown.com/lessons/essence-of-calculus); [Mathematics for Machine Learning](https://mml-book.github.io/); Blitzstein and Hwang, [Introduction to Probability](http://probabilitybook.net/); Chris Olah, [Visual Information Theory](https://colah.github.io/posts/2015-09-Visual-Information/).
- Proof: a notebook with PCA, linear regression in closed form and by gradient descent, and a maximum likelihood estimate, all in numpy, each tested against scikit-learn; entropy and KL divergence exercises.

### 2. Classical machine learning
- Material: Stanford [CS229](https://cs229.stanford.edu/) notes; chapters 8 to 12 of Mathematics for Machine Learning.
- Proof: logistic regression and k-means written from scratch; one entry in a tabular Kaggle competition, with the public score.

### 3. Deep learning
- Material: Andrej Karpathy, [Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html); Simon Prince, [Understanding Deep Learning](https://udlbook.github.io/udlbook/); optionally [fast.ai](https://course.fast.ai/).
- Proof: micrograd rewritten, with gradient tests against PyTorch; a makemore MLP that reaches the validation loss of the lecture; the notebooks on backpropagation and regularization.

### 4. Transformers and a language model built at home
- Material: 3Blue1Brown on [GPT](https://www.3blue1brown.com/lessons/gpt); [Attention Is All You Need](https://arxiv.org/abs/1706.03762); Karpathy's GPT and tokenizer lectures; Raschka's book; Stanford [CS336](http://cs336.stanford.edu/); Nathan Lambert's [RLHF book](https://rlhfbook.com/); the [DPO paper](https://arxiv.org/abs/2305.18290); the Hugging Face [LLM course](https://huggingface.co/learn/llm-course/chapter1/1); Karpathy's [nanochat](https://github.com/karpathy/nanochat).
- Proof: my own BPE tokenizer and GPT trained on a corpus I choose, with the loss curve; the same model after SFT and DPO, with an evaluation table before and after; CS336 assignments 1, 3, 4 and 5 with the course tests green; an open model adapted with LoRA to a task, evaluated before and after.

### 4b. Reinforcement learning basics
- Material: OpenAI [Spinning Up in Deep RL](https://spinningup.openai.com/en/latest/); chapter 2 of the [ARENA](https://learn.arena.education/) curriculum.
- Proof: a policy gradient and a PPO written from scratch that solve CartPole, with the reward curve.

### 5. Agents
- Material: Anthropic, [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents), [Effective context engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) and [Writing tools for agents](https://www.anthropic.com/engineering/writing-tools-for-agents); Thorsten Ball, [How to Build an Agent](https://ampcode.com/how-to-build-an-agent); [mini-swe-agent](https://github.com/SWE-agent/mini-swe-agent) and [SWE-bench](https://www.swebench.com/); the Berkeley [LLM Agents MOOC](https://llmagents-learning.org/f24); Hamel Husain, [Your AI product needs evals](https://hamel.dev/blog/posts/evals/); [Contextual Retrieval](https://www.anthropic.com/news/contextual-retrieval); the [Model Context Protocol](https://modelcontextprotocol.io/).
- Proof: an agent of my own in TypeScript, with the loop, tools to read, search and edit files and run commands, context management with compaction, permissions, code search with embeddings, and at least one MCP server. Measured on at least 50 SWE-bench tasks (share resolved) and on 10 real tasks I solved by hand beforehand.

### 6. Systems and GPUs
- Material: Google DeepMind, [How to Scale Your Model](https://jax-ml.github.io/scaling-book/); Hugging Face, [Ultra-Scale Playbook](https://huggingface.co/spaces/nanotron/ultrascale-playbook); CS336 assignment 2.
- Proof: a Triton kernel (fused softmax or the forward pass of FlashAttention) compared with PyTorch; assignment 2 with the course tests green.

### 7. Inference
- Material: the [PagedAttention paper](https://arxiv.org/abs/2309.06180); Raschka's KV cache bonus; the CS336 lecture on inference; the inference chapters of How to Scale Your Model.
- Proof: a KV cache in my own GPT, with tokens per second measured before and after.

### 8. Interpretability
- Material: [A Mathematical Framework for Transformer Circuits](https://transformer-circuits.pub/2021/framework/index.html); chapter 1 of ARENA.
- Proof: induction heads found in a small model, with the figure and the notebook public.

### 9. Safety and evaluations
- Material: [BlueDot Impact](https://bluedot.org/courses) courses; chapter 3 of ARENA (evaluations with Inspect); Evan Miller, [Adding Error Bars to Evals](https://arxiv.org/abs/2411.00640).
- Proof: an evaluation of my own written with Inspect and run on my model or my agent, with confidence intervals.

### Optional
- Multimodal models and diffusion (the CS336 lecture and the diffusion chapter of Prince's book); robustness to attacks (jailbreaks, adversarial training).

### 10. Reading the frontier, and contributing
- Material: S. Keshav, [How to Read a Paper](https://web.stanford.edu/class/ee384m/Handouts/HowtoReadPaper.pdf); Hugging Face [Daily Papers](https://huggingface.co/papers); the papers cited in modules 4 to 9.
- Proof: a one-page note for each paper read, one a week; a result of a recent paper reproduced at small scale every quarter; a first contribution, either a pull request accepted in an open source project or a published replication.

## Progress

| Module | Proof closed | Date |
|---|---|---|
| 0 Setup | - | - |
| 1 Math | - | - |
| 2 Classical ML | - | - |
| 3 Deep learning | - | - |
| 4 A language model at home | - | - |
| 4b Reinforcement learning | - | - |
| 5 Agents | - | - |
| 6 Systems and GPUs | - | - |
| 7 Inference | - | - |
| 8 Interpretability | - | - |
| 9 Safety and evaluations | - | - |
| 10 Frontier | - | - |

Count: 0 proofs closed, 0 stops published.

If you have walked this path before and think I should skip, add or reorder something, open an issue.
