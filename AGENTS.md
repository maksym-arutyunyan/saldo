# AGENTS.md

> DONE when all validation instructions reflect actual tooling and workflow.

## PR Naming

- Use Conventional Commits style for pull request titles  
  Example: `feat(cli): add init command`

## Validation

TODO 4: Review and update steps if your tool uses different build/test systems.

- If only documentation changes, skip build/test.
- If code changes:
  - `cargo build --release --all-targets`
  - `cargo test`
  - `cargo test --release`
  - `cargo clippy --all-targets -- -D warnings`
  - `cargo fmt --all -- --check`
  - Run project-specific validation checks (e.g. `<project>` on tracked files).
  - Run `./run-all.sh` to confirm consistency.

## Best Practices

- TODO 5: Create and commit rust-toolchain.toml to pin version.
- Keep configs sorted or linted.
- Update `CHANGELOG.md` for user-visible changes.
- Follow Conventional Commits for commits.

---

# Suggested Stack

> DONE when your project setup matches or updates the following stack.

- Language: Rust 2021 edition (TODO 5)
- CLI: clap (or other, if chosen differently) (TODO 6)
- Testing:
  - Unit tests with built-in framework.
  - Optionally, shell tests with `bats` (TODO 6)
- Lint/Format: `cargo fmt`, `cargo clippy`
- Automation: Single script to run all checks (`./run-all.sh`) (TODO 7)
- Changelog: `CHANGELOG.md` in Keep a Changelog format (TODO 12)
- Versioning: Semantic releases with GitHub Releases

---

# Project Phases

## Phase 1 – Setup & Minimal Structure

> DONE when specs.md, AGENTS.md, README.md, CI, and toolchain config are in place and validation passes.

### Goals

- Create skeletal repo with configs and placeholders

### Measurable Outcomes

- [ ] TODO 10: Validation script passes
- [ ] TODO 9: Minimal README, specs.md, AGENTS.md committed
- [ ] TODO 8: CI is configured

---

## Phase 2 – Early Functionality

> DONE when tool can do the smallest useful action with tests

### Goals

- Implement smallest testable feature
- Add basic unit test coverage

### Measurable Outcomes

- [ ] TODO 11: Core command or behavior is implemented
- [ ] CI passes on this behavior

---

## Phase 3 – Iterative Expansion

> Ongoing phase for gradual, reviewed progress

### Goals

- Add features or refactorings incrementally

### Measurable Outcomes

- [ ] TODO 13: CHANGELOG.md updated per PR
- Spec updated as needed
- CI remains green

---

## Phase 4 – Prototype Milestone

> DONE when users can try the project for real tasks

### Goals

- Provide real installable/testable version

### Measurable Outcomes

- [ ] TODO 14: Release tag (e.g. v0.1.0)
- Basic use cases documented in README

---

## Phase 5 – Polishing & Refinement

> DONE when all UX issues and edge cases are addressed

### Goals

- Improve error messages, docs, tests

### Measurable Outcomes

- [ ] TODO 15: README and CLI help are polished
- CHANGELOG reflects recent changes
- Full test coverage

---

## Phase 6 – Stable State

> Final phase for minimal-maintenance tools

### Goals

- Declare project stable

### Measurable Outcomes

- [ ] TODO 16: Version 1.0 (or similar) released
- `development-guide.md` exists with release steps

---

# Repository Hygiene

- `.gitignore` includes build artifacts, IDE, cache files
- Scripts (e.g. `run-all.sh`) reduce entry friction
- Exploratory code lives in `research/` or similar (optional)

---

# Commit Guidelines

Use [Conventional Commits](https://www.conventionalcommits.org/) throughout.

Examples:

- `feat(cli): add quiet flag`
- `fix(core): skip empty files`
- `chore(ci): update GitHub Actions`
