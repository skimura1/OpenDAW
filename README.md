# OpenDAW

🚧 **Early Development - Not Production Ready**

An open-source, cross-platform basic digital audio workstation built for
musicians, producers, and audio engineers who value freedom and flexibility.

OpenDAW is a lightweight DAW that combines intuitive workflow with powerful
audio processing capabilities. Rust brings memory safety and fearless
concurrency to audio processing.

## Key Features

**Multi-Track Audio Recording & Playback**  Record and play back multiple audio
tracks simultaneously with support for WAV, FLAC, and OGG formats.

**Built-in Effects Suite**  Simple built-in EQ, compression, reverb, delay, and
saturation. All effects are written in Rust with SIMD optimizations for
efficient CPU usage.

**Cross-Platform Compatibility**  Runs on Linux, macOS, and Windows with
consistent performance. Built with `cpal` for reliable audio I/O and `egui` for
a responsive, GPU-accelerated interface.

**Memory Safety by Design**  Rust's ownership system prevents entire classes of
bugs that plague traditional audio software. No more mysterious crashes during
that perfect take.

**Hackable & Extensible**  Clean, well-documented codebase makes it easy to add
features or customize behavior. Perfect for learning how DAWs work under the
hood or building your own audio tools.

## Installation

### Prerequisites

**Install Rust**

If you don't have Rust installed, get it from [rustup.rs](https://rustup.rs/):

```bash # Linux/macOS curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs
| sh

# Windows # Download and run rustup-init.exe from https://rustup.rs/ ```

After installation, restart your terminal and verify:

```bash rustc --version cargo --version ```

**System Dependencies**

Depending on your platform, you may need additional audio libraries:

*Linux (Ubuntu/Debian):* ```bash sudo apt-get update sudo apt-get install
libasound2-dev pkg-config ```

*Linux (Fedora):* ```bash sudo dnf install alsa-lib-devel pkg-config ```

*macOS:* ```bash # No additional dependencies needed - uses CoreAudio ```

*Windows:* ```bash # No additional dependencies needed - uses WASAPI ```

### Installation from Source

**Clone the Repository**

```bash git clone https://github.com/yourusername/opendaw.git cd opendaw ```

**Build and Run**

```bash # Development build (faster compilation, slower runtime) cargo run

# Release build (optimized for performance) cargo build --release
./target/release/opendaw ```

**Install Globally** (optional)

```bash cargo install --path . ```

This installs the binary to `~/.cargo/bin/` (make sure it's in your PATH).

### Installation from crates.io

Once published, you can install directly:

```bash cargo install opendaw ```

## Quick Start

After installation, launch OpenDAW:

```bash opendaw ```

1. **Create a new project** - File → New Project
2. **Add an audio track** - Track → New Audio Track
3. **Record** - Arm the track and press the record button
4. **Add effects** - Click on the track's effect chain to add built-in effects
5. **Export** - File → Export → WAV/FLAC/OGG

For detailed usage instructions, see the [User Guide](docs/USER_GUIDE.md).

## Troubleshooting

**"linker not found" error:**
- Install a C compiler (gcc/clang on Linux/macOS, MSVC on Windows)

**Audio device errors:**
- Check that your audio interface is connected and recognized
- Try running with `RUST_LOG=debug` for detailed logs

**Build fails on Linux:**
- Ensure you have `pkg-config` and ALSA development headers installed

## Running Tests

```bash cargo test ```

## Building Documentation

```bash cargo doc --open ```

## Contributing

We welcome contributions! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for
guidelines on:
- Reporting bugs
- Suggesting features
- Submitting pull requests
- Code style and testing requirements

## Support

- **Issues**: [GitHub Issues](https://github.com/yourusername/opendaw/issues)
- **Discussions**: [GitHub
Discussions](https://github.com/yourusername/opendaw/discussions)
- **Discord**: [Join our community](https://discord.gg/opendaw) (coming soon)

## Roadmap

- [ ] MIDI sequencing and piano roll editor
- [ ] VST3/LV2 plugin support
- [ ] Automation lanes
- [ ] Mixer view with advanced routing
- [ ] Real-time collaboration features
- [ ] Mobile companion app

## License

OpenDAW is licensed under the [MIT License](LICENSE).

## Acknowledgments

Built with:
- [cpal](https://github.com/RustAudio/cpal) - Cross-platform audio I/O
- [egui](https://github.com/emilk/egui) - Immediate mode GUI
- The amazing Rust audio community

---

**Built with Rust 🦀**
