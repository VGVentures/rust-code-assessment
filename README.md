# Rust Code Assessment

A Claude Code skill for structured technical audits of Rust projects, adapted from the [VGV Flutter Code Assessment](https://engineering.verygood.ventures/) methodology.

## Why

VGV's Flutter assessment has proven that repeatable, opinionated audits catch architectural drift before it becomes debt. Rust's compiler catches memory and concurrency bugs, but it doesn't enforce architectural discipline — a Rust project can compile cleanly while suffering from monolithic crates, concrete types everywhere, `.unwrap()` in production paths, and no CI gates.

This skill applies VGV's battle-tested principles (layered architecture, testability through injection, deterministic state, enforced quality gates) translated into Rust-native idioms.

## What It Does

Produces a `RUST_ASSESSMENT.md` with 10 sections covering:

1. **Architecture & Crate Structure** — workspace layout, trait-based DI, layered separation
2. **Error Handling** — `thiserror`/`anyhow`, documented error conditions, no silent failures
3. **Type Safety & Correctness** — newtypes, pattern matching, unsafe audit
4. **Async & Concurrency** — tokio patterns, cancellation safety, shared state
5. **Testing** — coverage (≥90%), isolation, descriptive names, behavior-driven
6. **CI/CD & Tooling** — clippy, fmt, deny, audit, conventional commits, semver
7. **API Design & Documentation** — visibility, rustdoc, Diataxis, `# Errors` sections
8. **Dependencies** — supply chain, bloat, compile time
9. **Performance & Resource Management** — allocation, I/O, observability
10. **Refactoring Estimation** — top risks, tasks, time estimates

## Usage

```
/rust-code-assessment <target_directory>
```

## Installation

Add to your Claude Code skills (personal or project level):

```bash
# Personal level (all projects)
cp -r .claude/skills/rust-code-assessment ~/.claude/skills/

# Project level (single project)
cp -r .claude/skills/rust-code-assessment your-project/.claude/skills/
```

## VGV Principle Mapping

| VGV Flutter Standard | Rust Equivalent |
|---|---|
| Feature-first directories | Crate-per-concern workspace |
| BLoC (state separation) | State machines + channels |
| Repository pattern (DI) | Trait-based injection |
| `very_good_analysis` | `clippy::pedantic` + `-D warnings` |
| 100% test coverage | `cargo-llvm-cov` ≥90% |
| `mocktail` | `mockall` or manual test doubles |
| Conventional Commits | Conventional Commits |
| Semantic Versioning | Semantic Versioning |

## References

- [VGV Engineering Best Practices](https://engineering.verygood.ventures/)
- [Notion Documentation](https://www.notion.so/31f45eb3279581bcba25ee6706e0399f)
- [Rust API Guidelines](https://rust-lang.github.io/api-guidelines/)

## License

MIT
