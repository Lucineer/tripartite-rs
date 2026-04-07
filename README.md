# Tripartite Consensus for Rust

Coordinate three specialized agents — Pathos, Logos, Ethos — that must all agree before a decision executes. An embeddable, privacy-first library for Rust, built for Cloudflare Workers. Zero dependencies. 🛡️

**Live Demo:** [https://tripartite-rs.casey-digennaro.workers.dev](https://tripartite-rs.casey-digennaro.workers.dev)

---

## Why This Exists
Single agents can miss context or make unreasonable choices. This library provides a structure where every automated decision is reviewed by three separate, specialized perspectives. It is designed for critical decisions where consensus is non-negotiable.

---

## Quick Start
1.  **Fork this repository.** This is fork-first software.
2.  Deploy to Cloudflare Workers in a few minutes using `wrangler`.
3.  Implement the `Agent` trait in `src/lib.rs` for your three specialized roles.

---

## Features
- **Unanimous Consensus:** No output is emitted unless all three agents vote affirmatively.
- **Generic `Agent` Trait:** You define the logic and data for each role.
- **Privacy-First:** All sensitive processing can stay local; the coordinator handles only agreement logic.
- **Edge Runtime:** Deploys globally on Cloudflare Workers with a low-latency edge runtime.
- **Single-File Core:** The entire consensus engine is contained in one Rust source file.
- **MIT Licensed:** No usage restrictions or proprietary dependencies.

---

## What Makes This Different
1.  **Unanimity Required:** There are no majority votes, tie-breakers, or lead agents. Full agreement is the only valid outcome.
2.  **Cloud Optional:** You can run all agents locally and use this coordinator solely for tamper-proof consensus validation.
3.  **You Own Your Fork:** Modify your copy without obligation to upstream changes. There is no lock-in.

---

## Limitations
The requirement for three separate agent evaluations increases overhead. For a given task, total computation time can be up to 3x that of a single-agent system, depending on your agent implementations.

---

## Development
You need the standard Rust toolchain and Wrangler.
```bash
# Install Wrangler
cargo install wrangler

# Run a local test server
wrangler dev

# Deploy to Cloudflare Workers
wrangler publish
```
All application logic is in `src/lib.rs`. Replace the example agents with your own models, business rules, or validation checks.

---

<div style="text-align:center;padding:16px;color:#64748b;font-size:.8rem"><a href="https://the-fleet.casey-digennaro.workers.dev" style="color:#64748b">The Fleet</a> &middot; <a href="https://cocapn.ai" style="color:#64748b">Cocapn</a></div>