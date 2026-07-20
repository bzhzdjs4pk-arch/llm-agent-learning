# LLM and Agent Learning Outline

## Phase 1 — Foundations (Weeks 1–2)

### Module 1: Essential Python and machine learning

Learn:

- Python data structures, functions, classes, typing, virtual environments, and testing
- NumPy basics and tensor shapes
- Train, validation, and test splits
- Loss functions, gradient descent, overfitting, and generalization
- Basic probability: distributions, conditional probability, and sampling

Practice:

- Implement linear regression with gradient descent.
- Write tests for data preprocessing functions.
- Compare training and validation curves.

### Module 2: How LLMs work

Learn:

- Tokens, tokenization, embeddings, and context windows
- Transformer blocks, self-attention, positional information, and feed-forward layers
- Pretraining, instruction tuning, preference optimization, and inference
- Sampling controls: temperature, top-p, stop conditions, and maximum tokens
- Model limitations: hallucination, context sensitivity, bias, and non-determinism

Build:

- A small notebook that tokenizes text and visualizes a simplified attention matrix.

Checkpoint:

- Explain the path from input text to generated token without relying on marketing language.

## Phase 2 — Building with LLMs (Weeks 3–4)

### Module 3: API and application fundamentals

Learn:

- Request/response anatomy, authentication, retries, timeouts, and streaming
- System instructions, user input, message history, and context management
- Structured outputs and schema validation
- Cost and latency measurement
- Secret management and environment configuration

Practice:

- Build a command-line chat application.
- Add exponential backoff and clear error handling.
- Log token usage, latency, and estimated cost without logging secrets.

### Module 4: Prompt and context design

Learn:

- Clear task definitions, constraints, examples, and output contracts
- Zero-shot, few-shot, decomposition, and critique/revision patterns
- Prompt injection and the separation of instructions from untrusted data
- When to use code, retrieval, fine-tuning, or a different model instead of more prompting

Build:

- A structured document extractor that returns validated JSON.
- A test set of at least 30 representative and adversarial examples.

Checkpoint:

- Reach a defined accuracy target and document the remaining failure modes.

## Phase 3 — Retrieval and RAG (Weeks 5–6)

### Module 5: Embeddings and search

Learn:

- Embedding spaces and similarity metrics
- Keyword, semantic, and hybrid search
- Chunking strategies and metadata filtering
- Indexing, reranking, deduplication, and freshness

Practice:

- Compare keyword and semantic retrieval on the same questions.
- Measure retrieval recall before measuring answer quality.

### Module 6: Retrieval-augmented generation

Learn:

- Ingestion, retrieval, context assembly, generation, and citation flow
- Query rewriting and multi-query retrieval
- Grounded answers, abstention, and source attribution
- Common RAG failures: missing evidence, noisy context, stale content, and fabricated citations

Build:

- A knowledge assistant over a small document collection.
- Require citations and an explicit “insufficient evidence” response.
- Create retrieval and answer-quality evaluations.

Checkpoint:

- Demonstrate which failures come from retrieval and which come from generation.

## Phase 4 — Agents (Weeks 7–9)

### Module 7: Tools and workflows

Learn:

- Function/tool definitions, input schemas, outputs, and error contracts
- Workflow, router, planner, and agent patterns
- State machines, loops, stopping conditions, and idempotency
- Human approval for consequential actions

Practice:

- Give an LLM two read-only tools and evaluate tool selection.
- Add invalid-input handling, timeouts, and retry limits.

### Module 8: Memory and state

Learn:

- Conversation state versus durable memory
- Working memory, episodic memory, and semantic memory
- Summarization, retrieval, expiration, and user control
- Privacy risks and data retention boundaries

Practice:

- Implement explicit session state.
- Compare full-history, summary, and retrieval-based memory.

### Module 9: Multi-step agent systems

Learn:

- Planning and plan repair
- Reflection and verification without unbounded loops
- Single-agent versus multi-agent tradeoffs
- Sandboxing, permissions, budgets, and audit trails

Build:

- A research agent that plans, uses read-only tools, cites evidence, and produces a report.
- Enforce maximum steps, time, and cost.
- Add a human approval checkpoint before any write action.

Checkpoint:

- Compare the agent against a simpler fixed workflow on quality, latency, and cost.

## Phase 5 — Production and Capstone (Weeks 10–12)

### Module 10: Evaluation

Learn:

- Task-specific success criteria and evaluation datasets
- Exact-match, rubric, retrieval, tool-use, safety, latency, and cost metrics
- Model-based grading and its biases
- Regression tests, experiment tracking, and error analysis

Practice:

- Create a versioned evaluation set.
- Run a baseline and categorize every failure.
- Add automated checks for the highest-risk regressions.

### Module 11: Safety, reliability, and observability

Learn:

- Prompt injection, data exfiltration, excessive agency, and insecure tool use
- Least privilege, allowlists, approvals, isolation, and rate limits
- Tracing, structured logs, metrics, alerts, and feedback collection
- Fallbacks, graceful degradation, caching, and incident response

Practice:

- Threat-model the application.
- Test malicious and malformed inputs.
- Add traces for model calls, retrieval, tool calls, and final outcomes.

### Module 12: Deployment and capstone

Build one complete application, such as:

- A cited research assistant
- A customer-support copilot with escalation
- A codebase onboarding assistant
- A personal knowledge assistant with controllable memory

Required capstone elements:

- Clear problem statement and non-goals
- Architecture diagram and documented data flow
- Typed tool and output schemas
- Representative evaluation dataset and baseline
- Safety boundaries and human approval points
- Cost and latency budget
- Monitoring and failure-recovery plan
- Setup instructions and demo

Final review questions:

1. Does the system solve a real task better than a simple baseline?
2. Which failures are detectable, and which are silent?
3. What actions can the system take, and with whose authority?
4. How does it behave when a model, tool, or data source fails?
5. Can a new contributor reproduce the evaluation results?

## Ongoing study loop

For every new technique:

1. State the hypothesis.
2. Create a small representative test set.
3. Implement the simplest baseline.
4. Measure quality, latency, and cost.
5. Inspect failures rather than averages alone.
6. Keep the change only if it improves the target outcome.

## Optional advanced topics

- Fine-tuning and distillation
- Multimodal models
- Long-context strategies
- Model routing and cascades
- Synthetic data generation
- Knowledge graphs and graph retrieval
- Local and open-weight model serving
- Agent interoperability protocols
- Reinforcement learning for agents
