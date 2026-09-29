Howdy!

Software engineer with 9+ years building and operating production systems, end to end:
architecture, implementation, the deployment pipeline, and the pager afterward. I reach
for the simplest thing that fits the problem, and I have shipped enough different stacks
to have opinions about which one that is.

I work in agentic engineering daily, partnering with coding agents to architect, review,
and ship production code, and I build the AI systems themselves: LLM-integrated
applications, RAG, and tools designed to be driven by agents. It changed my leverage more
than anything else in the last decade. I move faster on implementation and spend more
energy on system design, technical decision-making, and the work that compounds.

Most of my career has been in higher education, building admissions systems, student
information system integrations, and identity infrastructure across multiple
institutions, largely in PHP and Laravel. I consolidated SSO for a dozen applications off
three mismatched protocols onto a single in-house SAML/OIDC library and migrated them
onto containerized Kubernetes. I designed a centralized integration framework that
generates documentation, execution, retries, and alerting from a declarative spec, and
won team buy-in to replace 50+ hand-rolled integrations in a legacy application. I have
also built a HIPAA-compliant patient portal and a reading education platform with an
OpenAPI-specified backend and a React/TypeScript frontend.

Outside of work I build distributed systems in Rust, which is where I get to care about
replication, delivery semantics, and storage in a way day-to-day product work rarely
asks for. Those are the projects below, and they run on infrastructure I maintain myself.

I own the full SDLC on a number of systems, coordinate intake, prioritization, and
process improvement for diverse stakeholder groups, and serve as an SME on org-wide AI
initiatives, translating engineering realities into leadership recommendations and
driving adoption across teams.

### Selected projects

- **[tracon](https://github.com/cosmicspork/tracon)**: A self-hosted control plane that supervises coding agents across a mesh of nodes. Each node keeps a full local replica and keeps working through a hub outage; the hub is authoritative for ordering, never for availability. One static Rust binary, on a laptop or a Kubernetes pod.
- **[kritee](https://github.com/cosmicspork/kritee)**: Laravel work-management app (accounting, tasks, time tracking) architected to expose every action as a tool for AI agents.
- **[svastha](https://github.com/cosmicspork/svastha)**: Self-custodial, end-to-end-encrypted personal medical records. A Rust trust contract compiled to native and WASM, a zero-knowledge relay that stores ciphertext and routing metadata only, and a Svelte PWA. Devices converge by pull, with last-write-wins that needs no shared clock.
- **[laravel-rag-chat](https://github.com/cosmicspork/laravel-rag-chat)**: Laravel RAG chat widget with SAML SSO, vector search, and a provider-agnostic LLM proxy (UNO capstone for a K-12 district).
- **[tabla](https://tabla.joshbowen.net)**: End-to-end-encrypted turn-based games over a zero-knowledge relay, [playable now](https://tabla.joshbowen.net). Hidden state without a trusted third party: a mental-poker tile deal with a verifiable shuffle, written from scratch in Rust.
- **[consulta](https://github.com/cosmicspork/consulta)**: A read-only SQL gateway that makes a production database safe to hand an untrusted caller. Single SELECT/WITH only, inside a read-only transaction that is never committed.
- **[homelab](https://github.com/cosmicspork/homelab)**: GitOps Kubernetes on DigitalOcean: Flux v2, SOPS + age secrets, cert-manager, ingress-nginx.

### What I'm working with

**Languages:** PHP, Python, Rust, TypeScript, plus SQL, Go, and Bash

**Frameworks:** Laravel, Livewire, Filament, Laminas, React, Svelte, Django

**Infrastructure:** Kubernetes, Helm, Flux, Kustomize, Docker, Podman, AWS, Azure, DigitalOcean, Cloudflare Workers, GitLab CI, GitHub Actions

**Systems:** Replication and convergence, delivery semantics and idempotency, optimistic concurrency, zero-knowledge relays, local-first sync, WASM, wire protocols pinned by test vectors

**Data:** PostgreSQL, MSSQL, MySQL, Oracle, SQLite, Redis, Salesforce, PeopleSoft
