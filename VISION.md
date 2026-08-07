# PAI Universe — Vision

## Mission
Build a unified, simple, secure, and monitored PAI Agentic OS: a distributed system of autonomous AI agents ("EVEs"), each mapped to a subdomain, operating at zero/low cost on Cloudflare + Vercel edge infrastructure, with Pi Network as the trust and payment layer.

## Core Principles
1. Zero-Cost Priority — leverage Cloudflare Workers free tier, Vercel free tier, and other free-tier cloud primitives before paying for infrastructure.
2. Subdomain-as-an-Agent — each subdomain under the PAI Universe corresponds to one EVE agent with an isolated workspace and isolated database (Durable Objects / D1 / KV per agent).
3. Cloud-Native / Edge-Ready — default runtime is workerd isolates (Cloudflare Workers). Experimental or paid harnesses (e.g. HarnessAgent, Vercel Sandbox) are explicitly excluded from Phase 0/1 until independently verified as production-ready.
4. Trust & Identity — Pi Network integration provides trust and payment rails; no new token is introduced. AxiomID / OpenIdentity protocols provide DID-based identity and verifiable credentials for agents and humans.
5. Honest Documentation — a Doc-Intelligence gate ensures documentation accurately reflects implemented functionality; no aspirational or misleading claims about capability status.
6. Modularity — protocols (ADP, PAI-Protocol, AIP) and skills (pai-skills, pai-atom) are decoupled, versioned, and independently deployable.

## Repository Topology
The organization has been consolidated from 33 to 27 repositories. Twelve subagents live as folders under `infrastructure/pai-agent/` rather than as separate repositories, preserving git history and reducing operational overhead of cross-repo coordination.

## Architecture Layers
- Identity Layer: AxiomID, OpenIdentity — DID, TrustChain, verifiable credentials.
- Protocol Layer: PAI-Protocol (PPP), ADP (Agent Discovery Protocol), protocol-stubs.
- Agent Runtime: pai-agent-kit (zero-cost SDK: Vectorize, R2, Durable Objects), pai-core.
- Gateway/MCP: pai-mcp, pai-gateways, pai-api-gateway.
- Memory: PAI-Memory (semantic memory, deterministic conflict resolution).
- Skills/Marketplace: pai-skills, pai-atom (immutable PaiSkill ABI).
- Tooling: pai-tools (Go monorepo: ppm, skillbuilder, pai-sam, pai-port), pai-cli.
- Applications: PiWorker, PAI-Gspace, PAI-Email-Agent, axiomid-piverify.
- Public Surface: pai-website, pai-docs, openidentity.md.

## Phase Plan
- Phase 0 (execution: CI wiring, API keys, deployments) remains BLOCKED until explicit greenlight from the founder.
- Documentation (this VISION.md and CREDITS.md) is produced first so all collaborators and agents share the same source of truth.

## Status
- Organization cleanup: complete.
- Architectural planning: complete.
- Documentation: in progress.
- Phase 0 execution: pending approval.

## External Standards Adopted (No Governance Join)
We do not join CNCF or transfer trademark/governance of PPP, OpenIdentity, or the agent kit to any foundation. Instead we adopt select open, zero-cost standards as dependencies to strengthen our honest, no-false-claims positioning:

1. CloudEvents (CNCF, Apache-2.0) — reused as the event envelope format for PPP payloads and logging.json, giving agent-to-agent messages a standard, interoperable shape.
2. in-toto / Sigstore — attach provenance (claim : commit hash : signer) to agent publishes, formalizing our git-hash + doc-check gate as a named, checkable standard referenced in README/doc-intelligence sections.
3. OpenTelemetry — unified trace/heartbeat format for the 12 subagents' sessions, giving us baseline observability without building custom tooling.
4. OpenFeature / OpenCost — deferred; adopt later only if/when feature flags or cost telemetry become necessary.

Rationale: these are consumed as libraries/specs, not memberships. Zero governance surface, zero IP risk, zero cost — while giving the TrustChain/doc-intelligence gate industry-recognized backing six months earlier than building bespoke equivalents.
