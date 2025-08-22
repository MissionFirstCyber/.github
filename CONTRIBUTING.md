# Contributing to Mission First Cyber

Thanks for helping improve Mission First Cyber (M1 Cyber) projects! We value **secure, testable, and maintainable** contributions.

This guide applies across our org. Some repos add extra steps—always check each repo’s `README.md`.

---

## Ways to contribute

- Report bugs and regressions
- Propose features or improvements
- Improve docs, examples, and tests
- Triage issues (reproduce, add context, suggest labels)
- Review PRs (constructive, actionable feedback)

---

## Ground rules

- **Security first:** no secrets, tokens, or customer data in code, issues, or PRs.
- **Professional conduct:** follow our [Code of Conduct](./CODE_OF_CONDUCT.md).
- **Small PRs:** keep changes focused; split large work into logical commits/PRs.
- **Reproducibility:** document prerequisites and add tests or verification steps.

---

## Getting started

1. **Fork** the repo and clone your fork.
2. Create a branch:
   ```bash
   git checkout -b feat/<topic>     # or fix/<topic>, docs/<topic>, chore/<topic>
   ```
3. (Recommended) Install **pre-commit** hooks if present:
   ```bash
   pipx install pre-commit || pip install pre-commit
   pre-commit install
   ```
4. Install repo-specific tools (see the project README)—examples below.

---

## Commit messages (Conventional Commits)

Structure: `type(scope): summary`

Types: `feat`, `fix`, `docs`, `test`, `refactor`, `perf`, `chore`, `ci`

Examples:
- `feat(zeek): add dns tunneling detection`
- `fix(terraform): correct vcenter network name`
- `docs(fak): quickstart for air-gapped deploy`
- `ci(packer): validate templates on PR`

---

## Pull requests

**Before you open a PR**
- Rebase on `main`: `git fetch origin && git rebase origin/main`
- Run linters/formatters/tests
- Update docs/examples as needed
- Link issues: `Closes #123`

**PR must include**
- What changed & why
- Testing or verification steps (commands, PCAPs, screenshots)
- Security impact notes (if any)
- Migration/backwards-compat notes for breaking changes

Maintainers may label, request changes, or suggest follow-ups.

---

## Style & tooling (by area)

> Use repo-provided configs where available. If in doubt, match existing style.

### General
- Markdown: `markdownlint`
- YAML: `yamllint`
- Shell: `shellcheck`, POSIX-sh compatible unless otherwise stated
- JSON/NDJSON: validate with `jq`

### Terraform
- Format/validate:
  ```bash
  terraform fmt -recursive
  terraform validate
  tflint
  ```
- **No secrets** in state or VCS. Use backends and environment-specific workspaces.
- Provide `*.tfvars.example` with sane defaults; do **not** commit real `*.tfvars`.
- Prefer modules; document required variables and outputs.

### Packer (HCL2)
- Validate/build:
  ```bash
  packer fmt -recursive
  packer validate .
  ```
- Use variables; provide `example.pkrvars.hcl`.
- Don’t bake secrets into images; parameterize credentials.
- Note target builders (e.g., vSphere/Proxmox) in README.

### Ansible
- Lint & test:
  ```bash
  ansible-lint
  # If supported:
  molecule test
  ```
- Follow roles structure; idempotent tasks; avoid shell where modules exist.
- Vars precedence: keep defaults in `defaults/`, restrict `vars/` usage.

### Detection content (Zeek/Suricata/Security Onion)
- Include sample PCAPs **or** deterministic test cases when possible.
- Provide rationale, references, and expected signal/noise tradeoffs.
- Use stable IDs/filenames; document fields and dashboards affected.

---

## Testing & verification

- Include **exact commands** to reproduce and verify behavior.
- For infra changes, prefer ephemeral environments or local runners.
- For NSM content, include hashes for PCAPs and expected alert counts.

---

## Documentation expectations

- Every feature/change that affects users includes docs updates.
- Keep quickstarts minimal; link to deep-dive docs if they exist.
- Add diagrams where they clarify flows (auth, data, network).

---

## Security & responsible disclosure

If you suspect a vulnerability, **do not** open a public issue.

- Email **security@missionfirstcyber.com** with details (affected repo/commit, impact, PoC, reproduction).
- See our full policy: [SECURITY.md](./SECURITY.md)

---

## Licensing & DCO

Unless noted otherwise, projects are **Apache-2.0** licensed.

We use the **Developer Certificate of Origin**. Sign off each commit:

```bash
git commit -s -m "feat: awesome change"
```

This appends:

```
Signed-off-by: Your Name <you@example.com>
```

---

## Issue triage labels (typical)

- `bug`, `enhancement`, `documentation`
- `security`, `needs-repro`, `blocked`
- `good first issue`, `help wanted`

---

## Communication

- General questions: GitHub Discussions (per repo or org)
- Security reports: **security@missionfirstcyber.com**

Thanks for contributing to secure, mission-ready software!
