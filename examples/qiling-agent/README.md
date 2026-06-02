# Example: qiling-agent Adoption

`qiling-agent` is a product repository. It can adopt this rule repository by:

1. Copying `AGENTS.template.md` to `AGENTS.md`.
2. Copying relevant personas into `docs/agents/`.
3. Copying relevant rules into `docs/rules/`, `docs/design/`, or `docs/engineering/`.
4. Adding product-specific rules such as domain workflow, customer data handling, and AI output constraints.

Product repositories should keep business-specific rules local while keeping reusable engineering rules aligned with this repository.

Recommended install order for a repository like `qiling-agent`:

```text
1. copy AGENTS.template.md -> AGENTS.md
2. enable Chief Orchestrator as the default controller
3. copy only the personas needed for the current stage
4. copy orchestration, backend, frontend, testing, documentation, and git workflow rules
5. create docs/specs, docs/architecture, docs/design, docs/testing, docs/agents
6. write PRD + architecture + API contract before real integrations
7. run one real vertical slice through implement -> verify -> review -> push
```

For a repository that starts from zero, use:

- [project-bootstrap-checklist.md](/d:/项目git/agent-project-rules/playbooks/project-bootstrap-checklist.md)

For a repository that already exists, use:

- [existing-project-adoption-checklist.md](/d:/项目git/agent-project-rules/playbooks/existing-project-adoption-checklist.md)

Suggested reference in product README:

```text
This project uses reusable AI development rules from heqiucheng/agent-project-rules, with project-specific rules in AGENTS.md.
```
