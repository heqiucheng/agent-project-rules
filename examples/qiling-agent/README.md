# Example: qiling-agent Adoption

`qiling-agent` is a product repository. It can adopt this rule repository by:

1. Copying `AGENTS.template.md` to `AGENTS.md`.
2. Copying relevant personas into `docs/agents/`.
3. Copying relevant rules into `docs/rules/`, `docs/design/`, or `docs/engineering/`.
4. Adding product-specific rules such as domain workflow, customer data handling, and AI output constraints.

Product repositories should keep business-specific rules local while keeping reusable engineering rules aligned with this repository.

Suggested reference in product README:

```text
This project uses reusable AI development rules from heqiucheng/agent-project-rules, with project-specific rules in AGENTS.md.
```