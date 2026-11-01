# Contributing

Thank you for your interest in contributing to **helancode**.

helancode is a lightweight, extensible AI coding harness designed to provide a sophisticated developer experience through a focused runtime, efficient tool execution, and well-defined system boundaries.

We value simplicity, correctness, performance, security, and maintainable engineering.

This document describes how to set up the development environment, contribute changes, and submit pull requests.

## 1. Contribution Philosophy

We welcome contributions that improve the project without compromising its design principles.

Our engineering principles:

- **Minimalism over complexity:** Prefer simple solutions over unnecessary abstractions.
- **Explicit over implicit:** Keep runtime behavior predictable and observable.
- **Performance-conscious:** Avoid unnecessary allocations, blocking operations, and expensive dependencies.
- **Modular architecture:** Keep components independently understandable and testable.
- **Security by design:** Treat external input, tool execution, filesystem access, and model output as untrusted.
- **Backward compatibility:** Avoid breaking existing interfaces without a documented reason.
- **Maintainability:** Optimize for code that other developers can understand and extend.

A contribution does not need to introduce a feature. Bug fixes, tests, documentation improvements, performance optimizations, and architectural improvements are equally valuable.

## 2. Before Contributing

Before starting work:

1. Search existing issues and pull requests to avoid duplicate work.
2. For significant features, open an issue or discussion first.
3. Describe the problem before proposing an implementation.
4. Wait for maintainer feedback when a change affects architecture, public APIs, or core runtime behavior.

Small documentation fixes and isolated bug fixes can generally be submitted directly.

## 3. Development Environment

### Prerequisites

- Rust stable toolchain
- Cargo
- Git
- A supported operating system
- A code editor with Rust Analyzer support (recommended)

Install Rust using [rustup](https://rustup.rs/).

Install the required Rust components:

```bash
rustup component add rustfmt clippy
```

Verify the installation:

```bash
rustc --version
cargo --version
cargo clippy --version
```

### Clone the repository

```bash
git clone https://github.com/Emmanuel-Arokiaraj/helancode.git
cd REPO
```

Build the project:

```bash
cargo build
```

Run the application:

```bash
cargo run
```

## 4. Development Standards

### Rust conventions

Follow standard Rust conventions and idiomatic practices.

- Prefer ownership and borrowing over unnecessary cloning.
- Avoid unnecessary heap allocations.
- Use appropriate error types and explicit error propagation.
- Avoid panics in normal application execution paths.
- Prefer `Result<T, E>` for recoverable failures.
- Use `Option<T>` to represent optional values.
- Avoid unnecessary `unsafe` code.
- Document public APIs and non-obvious behavior.
- Avoid introducing dependencies for functionality that can reasonably be implemented with existing components or the standard library.

### Architecture

Keep responsibilities separated.

Examples of logical boundaries include:

- Agent runtime and orchestration
- Model provider integrations
- Context and conversation management
- Tool registry and execution
- Filesystem operations
- Terminal user interface
- Configuration and session management

These are conceptual boundaries, not requirements to create a crate or module for every component.

Avoid circular dependencies and unnecessary coupling between subsystems.

New abstractions should solve a demonstrated problem rather than anticipate speculative requirements.

### Error handling

- Do not silently swallow errors.
- Preserve useful error context.
- Avoid exposing secrets or sensitive information in logs.
- Distinguish recoverable failures from fatal failures.
- Do not use panics as a substitute for ordinary error handling.

### Dependencies

Before adding a dependency:

1. Verify that the functionality is necessary.
2. Check maintenance activity and release history.
3. Review licensing and transitive dependencies.
4. Consider binary size and compilation impact.
5. Consider whether existing dependencies already provide the functionality.

Do not introduce large dependencies for small or isolated requirements without justification.

## 5. Branching Strategy

Use descriptive branch names.

Recommended conventions:

```text
feature/<short-description>
fix/<short-description>
refactor/<short-description>
docs/<short-description>
perf/<short-description>
test/<short-description>
```

Examples:

```text
feature/tool-execution-engine
fix/session-restoration
refactor/provider-registry
perf/context-compaction
docs/architecture-overview
```

Avoid committing directly to the main branch.

## 6. Commit Messages

Use clear, descriptive commit messages.

We recommend Conventional Commits:

```text
feat: add tool execution engine
fix: resolve session restoration failure
refactor: simplify provider registry
perf: optimize context serialization
docs: document runtime architecture
test: add tool execution integration tests
chore: update dependencies
```

Keep commits focused on logically related changes.

## 7. Code Quality and Validation

Before submitting a pull request, run:

```bash
# Formatting
cargo fmt --all

# Compilation and type checking
cargo check --all-targets --all-features

# Linting
cargo clippy --all-targets --all-features -- -D warnings

# Tests
cargo test --all-features

# Production build
cargo build --release
```

All applicable checks should pass before submitting your contribution.

If a check cannot be executed locally, disclose the reason in the pull request.

### Testing expectations

- Add unit tests for new logic.
- Add integration tests for interactions between components.
- Include regression tests for bug fixes.
- Cover error paths and edge cases.
- Avoid tests that depend on external services unless explicitly designed as integration tests.
- Use mocks or deterministic test fixtures where appropriate.

Tests must not require real API credentials or expose private information.

## 8. Security Requirements

This project can interact with local files, shells, external tools, model providers, and potentially untrusted content.

Contributors must:

- Never hardcode API keys, tokens, or credentials.
- Never commit `.env` files containing secrets.
- Treat model output and tool arguments as untrusted input.
- Avoid introducing unrestricted command execution.
- Preserve existing permission and confirmation boundaries.
- Avoid logging sensitive prompts, credentials, or private file contents unnecessarily.
- Document security implications of changes involving execution, permissions, or filesystem access.

Do not weaken security controls to make tests pass.

Report suspected vulnerabilities through the process described in [SECURITY.md](SECURITY.md), not through public issues.

## 9. Pull Request Guidelines

Every pull request should:

- Have a clear description and motivation.
- Reference related issues where applicable.
- Explain important implementation decisions.
- Include relevant tests.
- Document public API or configuration changes.
- Identify breaking changes.
- Pass applicable CI checks.

Keep pull requests focused. Avoid combining unrelated features, refactoring, and formatting changes into one submission.

Maintainers may request revisions, additional tests, or architectural clarification before merging.

## 10. Documentation

Update documentation when a contribution changes:

- Public APIs
- Configuration options
- Runtime behavior
- Installation or setup procedures
- Tool execution behavior
- Architecture or module responsibilities
- User-facing commands

Examples should be accurate and executable wherever practical.

## 11. Review and Merge

All contributions are subject to maintainer review.

Maintainers may:

- Request changes.
- Suggest alternative implementations.
- Reject changes that conflict with project direction.
- Request additional testing.
- Close contributions that are incomplete, unsafe, or out of scope.

Submitting a pull request does not guarantee acceptance or a specific review timeline.

## 12. License

By submitting a contribution, you agree that your contribution will be distributed under the same license as this project.

You represent that you have the right to submit the contribution and that it does not knowingly violate third-party intellectual property rights.

Please review the repository's LICENSE file before contributing.

## 13. Community

We expect all contributors to follow our [Code of Conduct](CODE_OF_CONDUCT.md).

For questions and technical discussions, see [SUPPORT.md](SUPPORT.md).

Thank you for helping improve helancode.

**Build thoughtfully. Keep it lightweight. Make it reliable.**
