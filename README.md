Howdy!

I have been building and operating production systems for 10+ years. Below is what I've been building for myself recently. Most of it runs on infrastructure I maintain.

### [tracon](https://github.com/cosmicspork/tracon)

A self-hosted workspace for coding agents with a boundary around them. It supervises harnesses like Claude Code in a sandbox behind an egress allowlist, brokers credentials so agents can't read them, and publishes a GitHub PR or GitLab MR only after a person approves the diff and the agent's evidence. One static Rust binary, on a laptop or a Kubernetes pod. Built for how I want to work with agents.

**Built with:** Rust, Svelte, Tauri, containers, Kubernetes, MCP, end-to-end encryption, vector search

### [svastha](https://github.com/cosmicspork/svastha)

Self-custodial, end-to-end-encrypted personal medical records. A Rust trust contract compiled to native and WASM, a zero-knowledge relay that stores ciphertext and routing metadata only, and a Svelte PWA. Devices converge by pull, with last-write-wins. Keys derive from a seed phrase you hold, so no operator, including me, can read a record.

**Built with:** Rust, WASM, Svelte, PWA, end-to-end encryption, zero-knowledge relay, local-first sync

### [pager](https://github.com/cosmicspork/pager)

A communications archive and pager for Teams and Outlook web. A Chrome extension captures from signed-in tabs into a local Rust and SQLite archive that agents can search through read-only MCP. Notifications reach a phone end-to-end encrypted, through a self-hosted relay that only ever sees ciphertext. It shares its crypto core with svastha.

**Built with:** Rust, Chrome extension, SQLite, MCP, end-to-end encryption, Web Push, PWA

### [tabla](https://github.com/cosmicspork/tabla)

End-to-end-encrypted turn-based games over a zero-knowledge relay, [playable now](https://tabla.joshbowen.net). Hidden state without a trusted third party: a mental-poker tile deal with a verifiable shuffle, written from scratch in Rust.

**Built with:** Rust, WASM, SvelteKit, Cloudflare Workers, cryptography (mental poker)

### [kritee](https://github.com/cosmicspork/kritee)

Laravel work-management app (accounting, tasks, time tracking) architected to expose every action as a tool for AI agents. Every action runs as a user, the system, or an agent, and agent actions are logged and can be held in a review queue until a person approves them. Built for managing my own work.

**Built with:** Laravel, PHP, Livewire, Pest, Laravel Cloud

### [workboard](https://github.com/cosmicspork/workboard)

A local morning board for my own commitments, over a read-only Jira snapshot fetched through tracon's credential broker, so it never holds the Jira credential itself. It's built to become a tracon plugin once tracon supports plugins. TODO.txt yak-shaving in action.

**Built with:** Rust, SQLite, Svelte

### Small Python tools

[mesa](https://github.com/cosmicspork/mesa), [carta](https://github.com/cosmicspork/carta), [cuenta](https://github.com/cosmicspork/cuenta) and [consulta](https://github.com/cosmicspork/consulta) share one pattern: drop a Python file per source into `definitions/` and run. Each stops just short of acting, so a person makes the final call.

- **mesa** rebuilds a SQLite database from spreadsheets so they can be queried with SQL.
- **carta** runs SQL reports and writes Outlook drafts with the workbook attached. A person reviews and sends them.
- **cuenta** turns invoice PDFs into line-item JSONL for accounting import.
- **consulta** is a read-only SQL gateway for agents and other automated callers. It refuses anything but a single `SELECT`/`WITH` and runs it inside a read-only transaction that's never committed. It's not a replacement for a read-only database account.

**Built with:** Python, uv, pydantic, polars, SQLAlchemy, SQLite

### [homelab](https://github.com/cosmicspork/homelab)

GitOps Kubernetes on DigitalOcean: Flux v2, SOPS + age secrets, cert-manager, ingress-nginx. It runs the tracon hub and a node, image builds for tracon, the pager and svastha relays, and a few self-hosted apps (Immich, FreshRSS, PrivateBin).

**Built with:** Kubernetes, DigitalOcean, Flux, SOPS, cert-manager
