# Contributing to OpenDAW

First off, thank you for considering contributing to OpenDAW! It's people like
you that make OpenDAW such a great tool for the audio community.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Getting Started](#getting-started)
- [Development Setup](#development-setup)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)
- [Testing Guidelines](#testing-guidelines)
- [Community](#community)

## Code of Conduct

This project and everyone participating in it is governed by our [Code of
Conduct](CODE_OF_CONDUCT.md). By participating, you are expected to uphold this
code. Please report unacceptable behavior to
[conduct@opendaw.org](mailto:conduct@opendaw.org).

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check the existing issues to avoid
duplicates. When you create a bug report, include as many details as possible:

- **Use a clear and descriptive title**
- **Describe the exact steps to reproduce the problem**
- **Provide specific examples** - include code snippets, audio files, or
project files if relevant
- **Describe the behavior you observed** and what you expected to see
- **Include screenshots or recordings** if applicable
- **Specify your environment:**
  - OS (Linux distro/macOS version/Windows version)
  - Rust version (`rustc --version`)
  - OpenDAW version or commit hash
  - Audio interface/driver details

**Use our bug report template** when creating issues to ensure all necessary
information is included.

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an
enhancement suggestion:

- **Use a clear and descriptive title**
- **Provide a detailed description** of the suggested enhancement
- **Explain why this enhancement would be useful** to most OpenDAW users
- **List any similar features** in other DAWs if applicable
- **Include mockups or examples** if relevant

### Your First Code Contribution

Unsure where to begin? Look for issues labeled:

- `good first issue` - Simple issues perfect for newcomers
- `help wanted` - Issues where we need community help
- `documentation` - Improvements to docs, comments, or examples

### Pull Requests

We actively welcome your pull requests! Here's what we're looking for:

- **Bug fixes** - Always welcome
- **New effects or audio processing** - Great additions
- **UI/UX improvements** - Help make OpenDAW more intuitive
- **Performance optimizations** - Faster is better
- **Documentation** - Code comments, user guides, examples
- **Tests** - Improve coverage and reliability

## Getting Started

1. **Fork the repository** on GitHub
2. **Clone your fork** locally: ```bash git clone
https://github.com/your-username/opendaw.git cd opendaw ```
3. **Create a branch** for your changes: ```bash git checkout -b
feature/your-feature-name ```
4. **Make your changes** and commit them with clear messages
5. **Push to your fork** and submit a pull request

## Development Setup

### Prerequisites

- Rust 1.70 or later
- Platform-specific audio libraries (see README.md)
- A code editor with Rust support (VS Code + rust-analyzer recommended)

### Building

```bash # Debug build cargo build

# Release build (for performance testing) cargo build --release

# Run with logging RUST_LOG=debug cargo run ```

### Running Tests

```bash # Run all tests cargo test

# Run specific test cargo test test_name

# Run tests with output cargo test -- --nocapture ```

### Code Formatting

We use `rustfmt` for code formatting:

```bash # Format all code cargo fmt

# Check formatting without changing files cargo fmt -- --check ```

### Linting

We use `clippy` for linting:

```bash # Run clippy cargo clippy

# Run clippy with all warnings cargo clippy -- -W clippy::all ```

## Pull Request Process

1. **Update documentation** - Ensure README.md and code comments reflect your
changes
2. **Add tests** - Include tests for new functionality
3. **Run the test suite** - Ensure all tests pass with `cargo test`
4. **Format your code** - Run `cargo fmt` before committing
5. **Run clippy** - Address any warnings from `cargo clippy`
6. **Write clear commit messages** - Use present tense ("Add feature" not
"Added feature")
7. **Update CHANGELOG.md** - Add a note about your changes under "Unreleased"
8. **Create the PR** with a clear title and description:
   - Reference any related issues
   - Explain what changed and why
   - Include screenshots for UI changes
   - List any breaking changes

### PR Review Process

- Maintainers will review your PR within 1-2 weeks
- You may be asked to make changes before merging
- Once approved, a maintainer will merge your PR
- Your contribution will be credited in the release notes!

## Coding Standards

### General Guidelines

- **Write idiomatic Rust** - Follow Rust conventions and best practices
- **Keep functions focused** - Each function should do one thing well
- **Use descriptive names** - Variables and functions should be
self-documenting
- **Comment complex logic** - Explain the "why," not the "what"
- **Avoid unsafe code** unless absolutely necessary - document why it's needed

### Audio-Specific Guidelines

- **Never allocate in the audio thread** - Pre-allocate buffers where possible
- **Avoid locks in real-time code** - Use lock-free structures for audio
processing
- **Test with different buffer sizes** - Ensure code works with various audio
configurations
- **Profile performance** - Audio code should be efficient and predictable
- **Handle sample rate changes** - Don't assume 44.1kHz or 48kHz

### Code Organization

``` opendaw/ ├── src/ │   ├── audio/          # Audio engine and processing │
├── ui/             # GUI components │   ├── effects/        # Built-in effects
│   ├── project/        # Project management │   └── utils/          # Utility
functions ├── tests/              # Integration tests ├── docs/               #
Documentation └── examples/           # Example code ```

## Testing Guidelines

### Unit Tests

- Write tests for all new functions
- Test edge cases and error conditions
- Use descriptive test names: `test_compression_ratio_applied_correctly`

### Integration Tests

- Test workflows end-to-end
- Test audio processing with real audio data
- Verify UI interactions where possible

### Audio Testing

When testing audio processing:

```rust #[test] fn test_reverb_output() { let input =
generate_test_signal(440.0, 1.0); // 440Hz sine wave let mut reverb =
Reverb::new(44100); let output = reverb.process(&input);
    
// Verify output characteristics assert!(output.len() == input.len());
assert!(peak_level(&output) <= 1.0); } ```

## Community

### Communication Channels

- **GitHub Discussions** - General questions and discussions
- **GitHub Issues** - Bug reports and feature requests
- **Discord** - Real-time chat with the community (coming soon)

### Getting Help

Stuck? Here's how to get help:

1. Check existing documentation and issues
2. Ask in GitHub Discussions
3. Join our Discord community
4. Tag maintainers in your issue/PR if urgent

### Recognition

Contributors are recognized in:
- CHANGELOG.md for each release
- README.md acknowledgments section
- Annual contributor shoutouts

## Thank You!

Your contributions make OpenDAW better for everyone. We're excited to see what
you'll build! 🎵🦀
