# Responsible AI Skills

A curated collection of AI evaluation "skills" for reviewing applications that use LLMs and machine learning across ethics, privacy, safety, and security. Each skill contains scope, triggers, red flags, mitigations, and checklists to support automated or human-in-the-loop reviews.

**Skills**
- **Ethics**: Algorithmic bias, fairness, accessibility, and transparency. See [ethics/SKILL.md](ethics/SKILL.md).
- **Privacy**: PII, biometric data, consent, tracking, and data protection compliance. See [privacy/SKILL.md](privacy/SKILL.md).
- **Safety**: Harm to vulnerable populations and high-risk domains (healthcare, children, mental health). See [safety/SKILL.md](safety/SKILL.md).
- **Security**: Prompt injection, hardcoded secrets, data leakage, insecure output handling, and supply chain risks. See [security/SKILL.md](security/SKILL.md).

**How to use**
- Read the relevant `SKILL.md` to identify triggers and follow the provided assessment checklist.
- Use the response frameworks in each skill to create consistent findings and recommended fixes.
- Combine multiple skills for multidisciplinary reviews (for example, use both privacy and security checks for RAG systems).

**Evals**

- Location: Each skill keeps evaluation cases under `evals/evals.json` and related test assets under `evals/files/`.
- Format: `evals/evals.json` is a JSON array where each entry contains at minimum:
  - `id`: short eval identifier
  - `prompt`: code or scenario to present to the model
  - `expectations`: list of strings describing expected findings (used for automated or manual scoring)
- Purpose: Evals are example cases used to validate that a model (e.g., Claude) or human reviewer flags the correct issues and returns the expected severity, reasoning, and recommended mitigations.
- How they're used:
  - Automated runs: an evaluation harness can feed each `prompt` to the model and check the model's response against `expectations` to produce pass/fail metrics.
  - Manual review: reviewers can use the prompts as reproducible test cases or interview-style scenarios when auditing code or deployments.
  - Regression testing: keep evals to ensure future model/skill updates don't regress on key failure modes.
- Contributing new evals:
  - Add a new entry to the appropriate `evals/evals.json` with a unique `id`, clear `prompt`, and concrete `expectations`.
  - Place any supporting files (images, datasets, sample code) in `evals/files/` and reference them from the `prompt`.
  - Keep prompts focused and expectations actionable (severity + concrete checks).

**Contributing**
- Improve or extend individual `SKILL.md` files via pull requests. Keep changes focused (checklists, mitigations, or tooling references).
- Add tests and example snippets or evals when introducing new guidance.

---

Maintainers: See the individual skill files for detailed guidance and examples.
# Responsible AI Skills

A curated collection of AI evaluation "skills" for reviewing applications that use LLMs and Machine Learning across ethics, privacy, safety, and security. Each skill contains scope, triggers, red flags, mitigations, and checklists to support automated or human-in-the-loop reviews.

**Skills**
- **Ethics**: Algorithmic bias, fairness, accessibility, and transparency. See [ethics/SKILL.md](ethics/SKILL.md).
- **Privacy**: PII, biometric data, consent, tracking, and data protection compliance. See [privacy/SKILL.md](privacy/SKILL.md).
- **Safety**: Harm to vulnerable populations and high-risk domains (healthcare, children, mental health). See [safety/SKILL.md](safety/SKILL.md).
- **Security**: Prompt injection, hardcoded secrets, data leakage, insecure output handling, and supply chain risks. See [security/SKILL.md](security/SKILL.md).

**How to use**
- Read the relevant `SKILL.md` to identify triggers and follow the provided assessment checklist.
- Use the response frameworks in each skill to create consistent findings and recommended fixes.
- Combine multiple skills for multidisciplinary reviews (for example, use both privacy and security checks for RAG systems).

**Contributing**
- Improve or extend individual `SKILL.md` files via pull requests. Keep changes focused (checklists, mitigations, or tooling references).
- Add tests and example snippets when introducing new guidance.

---

Maintainers: See the individual skill files for detailed guidance and examples.
