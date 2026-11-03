# Covela

A lightweight, fast **Dynamic Island for Windows 11**. Covela sits at the top of your screen as a small pill that expands to show what matters right now: media, notifications, battery, timers, and more.

> **Status:** early development. Covela is not usable yet. Features below are the plan, not the current state.

<!-- Add a demo GIF here once the first prototype works:
![Covela demo](docs/demo.gif)
-->

## Why Covela

- **Light on resources**: Rust core, small UI bundle, no background polling when idle
- **Smooth**: spring-based animations between idle, compact, and expanded states
- **Private**: everything stays on your machine, no telemetry, no account
- **Open source**: MIT licensed, built to be extended

## Planned features

**v0.1 (MVP)**
- [ ] Island with idle / compact / expanded states
- [ ] Media controls (title, artist, cover, play/pause/next)
- [ ] Battery and charging indicator
- [ ] Volume and brightness overlay
- [ ] Timer / Pomodoro
- [ ] Notifications (compact view)
- [ ] Settings: position, monitor, theme, launch at startup
- [ ] Auto-hide when an app is fullscreen

**Later**
- [ ] File shelf (drag and drop)
- [ ] Clipboard history
- [ ] Meeting / call status
- [ ] System monitor
- [ ] Custom themes and widgets

## Requirements

- Windows 11
- WebView2 runtime (included with Windows 11)

## Installation

Not available yet. Releases will be published on the
[Releases page](../../releases) once the first beta is ready.

## Development

### Prerequisites

- [Node.js](https://nodejs.org) (LTS) and [pnpm](https://pnpm.io)
- [Rust](https://rustup.rs) (MSVC toolchain)
- Visual Studio Build Tools 2022 with the **Desktop development with C++** workload

### Run locally

```bash
git clone https://github.com/<your-username>/covela.git
cd covela
pnpm install
pnpm tauri dev
```

### Build

```bash
pnpm tauri build
```

The installer is generated in `src-tauri/target/release/bundle/`.

## Tech stack

- [Tauri 2](https://tauri.app) (Rust core + WebView2)
- [Svelte](https://svelte.dev) + TypeScript
- [`windows`](https://crates.io/crates/windows) crate for Windows APIs

## Project structure

```
src/             UI (Svelte): island, widgets, settings
src-tauri/       Rust core: window management, providers, settings
  src/providers/ one module per feature (media, battery, audio, ...)
```

## Contributing

Contributions, bug reports, and ideas are welcome. Please open an issue first for larger changes so we can discuss the direction.

## License

[MIT](LICENSE)