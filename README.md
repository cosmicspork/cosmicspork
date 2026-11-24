Howdy!

I have been building and operating production systems for 10+ years. Below is what I've been building for myself recently: security boundaries for AI agents, and end-to-end-encrypted systems. Most of it runs on infrastructure I maintain.

### [tracon](https://github.com/cosmicspork/tracon)

A self-hosted workspace for coding agents with a boundary around them. It supervises harnesses like Claude Code in a sandbox behind an egress allowlist, brokers credentials so agents can't read them, and publishes a GitHub PR or GitLab MR only after a person approves the diff and the agent's evidence. One static Rust binary, on a laptop or a Kubernetes pod. Plugins add reviewable database and Jira access, plus a few other small apps. Built for how I want to work with agents.

**Built with:** Rust, Svelte, Tauri, containers, Kubernetes, MCP, end-to-end encryption, vector search

### Tracon plugins

Each runs as a plugin on a tracon node, and each also runs on its own.

- **[sql-review](https://github.com/cosmicspork/sql-review)** gives agents SQL. Keeps read and write credentials seperate and queues writes for review and approval.
- **[jira-review](https://github.com/cosmicspork/jira-review)** gives agents Jira. Queues writes for review and approval.
- **[workboard](https://github.com/cosmicspork/workboard)** a fancy TODO.txt with agent tools and links to Jira via a read-only snapshot.
- **[hora](https://github.com/cosmicspork/hora)** another review and approval queue to use with agents, for time tracking.
- **[hoja](https://github.com/cosmicspork/hoja)** I got tired of halucinations in documents co-authored by agents, so this adds yet another review and approval queue with some fancy tricks.

**Built with:** Rust, Svelte, SQLite, MCP, Typst

### [svastha](https://github.com/cosmicspork/svastha)

Self-custodial, end-to-end-encrypted personal medical records. A Rust trust contract compiled to native and WASM, a zero-knowledge relay that stores ciphertext and routing metadata only, and a Svelte PWA. Devices converge by pull, with last-write-wins. Keys derive from a seed phrase you hold, so no operator, including me, can read a record.

**Built with:** Rust, WASM, Svelte, PWA, end-to-end encryption, zero-knowledge relay, local-first sync

### [pager](https://github.com/cosmicspork/pager)

A communications archive and pager for Teams and Outlook web. A Chrome extension captures from signed-in tabs into a local Rust and SQLite archive that agents can search through read-only MCP. Notifications reach a phone end-to-end encrypted, through a self-hosted relay that only ever sees ciphertext. It shares its crypto core with svastha.

**Built with:** Rust, Chrome extension, SQLite, MCP, end-to-end encryption, Web Push, PWA

### [tabla](https://github.com/cosmicspork/tabla)

End-to-end-encrypted turn-based games over a zero-knowledge relay, [playable now](https://tabla.joshbowen.net). Hidden state without a trusted third party: the tiles are dealt with a mental-poker protocol and a verifiable shuffle, implemented in Rust.

**Built with:** Rust, WASM, SvelteKit, Cloudflare Workers, cryptography (mental poker)

### Small Python tools

[mesa](https://github.com/cosmicspork/mesa), [carta](https://github.com/cosmicspork/carta) and [cuenta](https://github.com/cosmicspork/cuenta) share one pattern: drop a Python file per source into `definitions/` and run. Each stops just short of acting, so a person makes the final call.

- **mesa** rebuilds a SQLite database from spreadsheets so they can be queried with SQL.
- **carta** runs SQL reports and writes Outlook drafts with the workbook attached. A person reviews and sends them.
- **cuenta** turns invoice PDFs into line-item JSONL for accounting import.

**Built with:** Python, uv, pydantic, polars, SQLAlchemy, SQLite

### [homelab](https://github.com/cosmicspork/homelab)

GitOps Kubernetes on DigitalOcean: Flux v2, SOPS + age secrets, Cloudflare Tunnel for ingress, and VolSync backups to R2. It runs the tracon hub and a node, image builds for tracon, the pager and svastha relays, and a few self-hosted apps (Immich, FreshRSS, and a Minecraft server for my modpack).

**Built with:** Kubernetes, DigitalOcean, Flux, SOPS, Cloudflare Tunnel, VolSync
