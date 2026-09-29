Howdy!

I'm a software engineer with 9+ years building and operating production systems end to
end: architecture, implementation, the deployment pipeline, and what happens after
deploy. I own the full SDLC on a number of systems, which puts me as close to the people
who depend on them as to the code: coordinating intake and priorities with stakeholder
groups, finding the process improvements hiding in their day, and translating engineering
realities into recommendations leadership can act on. I reach for the simplest thing that
fits the problem, and I have shipped enough different stacks to have opinions about which
one that is.

Lately that has meant AI. I serve as an SME on org-wide AI initiatives and drive adoption
across teams, and I work with coding agents daily to architect, review, and ship
production code. I also build the AI systems themselves: LLM-integrated applications,
RAG, and tools designed to be driven by agents. Nothing in the last decade has changed my
leverage more. I move faster on implementation and spend more of my energy on system
design and the decisions that compound.

On my own time I build distributed systems in Rust, where I get to care about
replication, delivery semantics, and storage in a way day-to-day product work rarely asks
for. Those are most of the projects below, and they run on infrastructure I maintain
myself.

### Selected projects

- **[tracon](https://github.com/cosmicspork/tracon)**: A self-hosted workspace for coding agents, and the boundary around them. It supervises Claude Code and OpenCode in sandboxed harnesses behind an egress allowlist, brokers credentials so agents never hold them, and publishes a GitHub PR or GitLab MR only after a human approves the diff and its evidence. Nodes form a mesh: each keeps a full local replica and keeps working through a hub outage; the hub is authoritative for ordering, never for availability, and cannot read channels it was never given a key to. Conflicts stay pairwise (site-stamped writes, HLC last-write-wins, tombstones), and vector search runs per node because embeddings never replicate. One static Rust binary, on a laptop or a Kubernetes pod.
- **[kritee](https://github.com/cosmicspork/kritee)**: Laravel work-management app (accounting, tasks, time tracking) architected to expose every action as a tool for AI agents.
- **[svastha](https://github.com/cosmicspork/svastha)**: Self-custodial, end-to-end-encrypted personal medical records. A Rust trust contract compiled to native and WASM, a zero-knowledge relay that stores ciphertext and routing metadata only, and a Svelte PWA. Devices converge by pull, with last-write-wins that needs no shared clock.
- **[laravel-rag-chat](https://github.com/cosmicspork/laravel-rag-chat)**: Laravel RAG chat widget with SAML SSO, vector search, and a provider-agnostic LLM proxy (UNO capstone for a K-12 district).
- **[tabla](https://tabla.joshbowen.net)**: End-to-end-encrypted turn-based games over a zero-knowledge relay, [playable now](https://tabla.joshbowen.net). Hidden state without a trusted third party: a mental-poker tile deal with a verifiable shuffle, written from scratch in Rust.
- **[consulta](https://github.com/cosmicspork/consulta)**: A read-only SQL gateway that makes a production database safe to hand an untrusted caller. Single SELECT/WITH only, inside a read-only transaction that is never committed.
- **[homelab](https://github.com/cosmicspork/homelab)**: GitOps Kubernetes on DigitalOcean: Flux v2, SOPS + age secrets, cert-manager, ingress-nginx.

### What I'm working with

**Languages:** Bash, Go, PHP, Python, Rust, SQL, TypeScript

**Frameworks:** Django, Filament, Laminas, Laravel, Livewire, React, Svelte

**Infrastructure:** AWS, Azure, Cloudflare Workers, DigitalOcean, Docker, Flux, GitHub Actions, GitLab CI, Helm, Kubernetes, Kustomize, Podman

**Systems:** Delivery semantics and idempotency, local-first sync, optimistic concurrency, replication and convergence, WASM, wire protocols pinned by test vectors, zero-knowledge relays

**Data:** MSSQL, MySQL, Oracle, PeopleSoft, PostgreSQL, Redis, Salesforce, SQLite
