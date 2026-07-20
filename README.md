# LLM Mastery: LLM and Agent Learning Path

A practical, project-based roadmap for learning large language models (LLMs) and AI agents—from foundations to reliable production systems.

## How to use this repository

- Follow the modules in order if you are new to the field.
- Spend roughly 5–8 hours per week for 12 weeks.
- Build the suggested project in each phase; reading alone is not enough.
- Record experiments, prompts, evaluations, failures, and lessons learned.

## Learning outcomes

By the end of this path, you should be able to:

- Explain how transformers and LLM inference work at a practical level.
- Design prompts and structured outputs for dependable applications.
- Build retrieval-augmented generation (RAG) systems.
- Create tool-using agents with explicit state and control flow.
- Evaluate quality, cost, latency, safety, and reliability.
- Deploy and monitor an LLM or agent application.

## Roadmap

The detailed curriculum is in [LEARNING_OUTLINE.md](LEARNING_OUTLINE.md). Start with
[Module 1: Environment, Python, and the LLM landscape](modules/01-environment-and-python/README.md),
which includes verified video, course, reading, and code links.

| Phase | Weeks | Focus | Deliverable |
| --- | ---: | --- | --- |
| Foundations | 1–2 | Python, ML concepts, transformers | Token and attention notebook |
| LLM applications | 3–4 | APIs, prompting, structured outputs | Document extraction app |
| Retrieval | 5–6 | Embeddings, search, RAG | Cited knowledge assistant |
| Agents | 7–9 | Tools, state, workflows, memory | Research agent |
| Production | 10–12 | Evaluation, safety, observability, deployment | Evaluated capstone |

## Suggested repository structure

```text
.
├── README.md
├── LEARNING_OUTLINE.md
├── modules/
│   └── 01-environment-and-python/
│       └── README.md
├── notes/
├── exercises/
├── projects/
│   ├── structured-extractor/
│   ├── rag-assistant/
│   └── research-agent/
└── evals/
```

## Progress tracker

- [ ] [Module 1: Environment, Python, and the LLM landscape](modules/01-environment-and-python/README.md)
- [ ] Phase 1: Foundations
- [ ] Phase 2: Building with LLMs
- [ ] Phase 3: Retrieval and RAG
- [ ] Phase 4: Agents
- [ ] Phase 5: Production and capstone

## Learning principles

1. Start with the simplest workflow that can solve the task.
2. Prefer deterministic code for deterministic work.
3. Treat prompts, tools, data, and model versions as application dependencies.
4. Evaluate with representative examples before optimizing.
5. Make failures visible and design recovery paths.

## License

This learning outline is available under the [MIT License](LICENSE).
