# What's New in Rust — Briefing Digest

**Version:** Rust 1.100.0 — "Announcing Rust 1.100.0"
**Release date:** 12 November 2026
**Primary source:** Official Rust blog post — [Announcing Rust 1.100.0](https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/)

## Headline features
- **Never type (`!`) is stable** — the canonical uninhabited type, finally stable after ~10 years / 5 failed attempts. Can be used anywhere (`Result<T, !>`, named in return types). `Infallible` now aliases `!`.
- **`Allocator` API** — core parts stabilized (`Allocator` trait, `Vec::new_in`, `Box::new_in`).
- **`DropGuard`** — `core::mem::DropGuard` runs a closure on every exit path; `DropGuard::dismiss`.
- **`std::mem::conjure_zst`** — unsafe function to create zero-sized types.
- **Cargo unused dependency reporting** — warns on `unused_dependencies` lint (default warn).
- **Cargo cache collision reduction** — build-dir now consistently applies build-configuration hash.
- **Cargo min-publish-age** — opt-in dependency cooldowns for supply-chain protection.

## Breaking / action items
- **Never-type fallback change:** in editions before 2024 (2015, 2018, 2021), the fallback type for unconstrained never expressions changes from `()` to `!` (like edition 2024). Rare cases (ignoring generic function results) may change more code as unreachable.
- Others: Cargo build-dir layout changed (not a stable interface); `box` patterns no longer parsed; unusual closures in `if let` may trigger new borrow errors; ARM ABI changes hard errors downgrade tier-2 targets.

## Community reception
- Positive and widely covered: the never-type stabilization is the "biggest change" in the release. Secondary write-ups (TecAdmin, ostechnix) and LWN.net features it as one of the many stabilized features. Official Rust blog published announcement and compatibility notes.

## Sources
- Primary: [Rust Blog — Announcing Rust 1.100.0](https://blog.rust-lang.org/2026/11/12/Rust-1.100.0/)
- Secondary 1: [Rust 1.100 Released: Never Type, Allocators & What's New](https://tecadmin.net/rust-1-100-released-whats-new/)
- Secondary 2: [Rust 1.100.0 Released: New Features and Cargo Improvements](https://ostechnix.com/rust-1-100-0-new-features/)
- Secondary 3 (news): [The Rust Release Announcements](https://blog.rast-lang.org/releases/)

## GitHub inbox housekeeping
- No unread Rust-release notification found in the account inbox (notifications list returned empty).
