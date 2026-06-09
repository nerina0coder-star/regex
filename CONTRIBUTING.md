# Contributing to FunctionMatcher

Thank you for your interest! This is a niche regex project, but improvements are welcome.

## How to help

- **Test the regex** with RE2 on various inputs and report issues.
- **Add more function names** to the allowed list (see `calc|find_chambers|...`).
- **Improve documentation** – examples, diagrams, performance notes.
- **Create bindings** for other languages that support RE2 (Go, Rust, C++).

## Before opening an issue

- Search existing issues.
- Be sure you're using Google RE2, not Python's `re`.
- Provide a minimal failing input and expected output.

## Pull request process

1. Fork the repo.
2. Create a branch (`git checkout -b improve-regex`).
3. Make your changes.
4. Run tests (if any exist – we need test cases!).
5. Open a PR describing what you changed and why.

## Code of Conduct

Please follow our [Code of Conduct](CODE_OF_CONDUCT.md).
