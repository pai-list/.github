# PAI Universe — Credits & Attributions

## Founder
- Mohamed Abdelaziz (@Moeabdelaziz007) — Founder, PAI Universe. Architect of AxiomID, PAI-Protocol, and the PAI Agentic OS vision.

## Open Standards Adopted
The PAI Universe does not join or transfer governance to any foundation (e.g. CNCF). Instead, we consume the following open standards as libraries/specs, retaining full control of our own trademarks and governance:

- CloudEvents (CNCF, Apache-2.0) — event envelope format used in PPP payloads and logging.json.
- in-toto / Sigstore — provenance/claim verification pattern (claim : commit hash : signer) underlying our doc-intelligence and TrustChain gates.
- OpenTelemetry — trace/heartbeat format for subagent observability.
- W3C DID / Verifiable Credentials — identity primitives underlying AxiomID and OpenIdentity.

## Infrastructure Providers
- Cloudflare (Workers, Durable Objects, D1, R2, Vectorize, KV) — primary zero-cost edge runtime.
- Vercel — hosting for Next.js applications (pai-website, and others).
- GitHub — source control, CI/CD (Actions), and organizational hosting.
- Pi Network — trust and payment layer for agent-to-agent and agent-to-human transactions.

## AI Collaborators
This project is built in collaboration with multiple AI coding and research agents, working under the founder's direction for code generation, architectural review, and documentation drafting:

- **opencode** — primary interactive coding agent.
- **Hermes** — local research & coding agent pipeline.
- **Jules AI** — cloud agentic coding assistant.
- **CodeRabbit AI** — automated code review.
- **Antigravity** — development environment / IDE.
- **Claude, Gemini, Grok, GitHub Copilot** — code generation, architectural review, and documentation drafting.

## Evaluated / Deferred Tools
- **Zerolang (zerolang.ai, Vercel Labs)** — experimental graph-native language for agents (Apache-2.0). Evaluated and explicitly **deferred**: not used in Phase 0/1, and it is **not** an AI collaborator. Revisit only after it leaves experimental status, per the same exclusion rule as HarnessAgent and Vercel Sandbox.

## License Note
Individual repositories retain their own licenses (see each repo's LICENSE file, typically MIT). This CREDITS.md documents external standards and infrastructure dependencies, not a transfer of ownership or governance.
