# Rust Code Assessment

A Claude Code skill for structured technical audits of Rust projects, adapted from the [VGV Flutter Code Assessment](https://verygood.ventures) methodology.

## What It Does

Produces a `RUST_ASSESSMENT.md` with 10 sections covering:

1. **Architecture & Crate Structure** — workspace layout, trait-based DI
2. **Error Handling** — `thiserror`/`anyhow`, no silent failures
3. **Type Safety & Correctness** — newtypes, pattern matching, unsafe audit
4. **Async & Concurrency** — tokio patterns, cancellation safety, shared state
5. **Testing** — coverage, isolation, property testing
6. **CI/CD & Tooling** — clippy, fmt, deny, audit
7. **API Design & Documentation** — visibility, rustdoc, API guidelines
8. **Dependencies** — supply chain, bloat, compile time
9. **Performance & Resource Management** — allocation, I/O, observability
10. **Refactoring Estimation** — top risks, tasks, time estimates

## Usage

```
/rust-code-assessment maxwell_server
```

## Installation

Add to your Claude Code skills (personal or project level):

```bash
# Personal level (all projects)
cp -r .claude/skills/rust-code-assessment ~/.claude/skills/

# Project level (single project)
cp -r .claude/skills/rust-code-assessment your-project/.claude/skills/
```

## Documentation

Full methodology and principles: [Notion Documentation](https://www.notion.so/31f45eb3279581bcba25ee6706e0399f)

## License

MIT
