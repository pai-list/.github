# 🌌 PAI Universe — Live Status & Evidence

> **Org:** [pai-list](https://github.com/pai-list) · **23 active** + 4 archived public repos (GitHub API, 2026-08-08)
> **Last verified:** 2026-08-08 — every row below re-checked live with the command shown; DOWN = NXDOMAIN/404, not intent.

## 🟢 Live Services (HTTP-verified 2026-08-08)

All subdomains resolve and serve 200 through the Cloudflare edge worker (`infrastructure/protocol-stubs`), except where noted.

| Service | URL | Verify | Status |
|---------|-----|--------|--------|
| Hub — Universal Entry Point | `https://axiomid.app/` | `curl -s -o /dev/null -w"%{http_code}" https://axiomid.app/` → **200** | 🟢 LIVE |
| Hub health | `https://axiomid.app/health` | → **200** `{"status":"healthy","protocol":"axiomid"}` | 🟢 LIVE |
| CaaS / MCP discovery | `https://axiomid.app/.well-known/mcp.json` | → **200** (JSON, protocol `publicmcp`) | 🟢 LIVE |
| Agent discoverability | `/agent.json` · `/llms.txt` · `/agentic.txt` · `/sitemap.xml` | all → **200** | 🟢 LIVE |
| Skills registry (4-lang) | `https://skills.axiomid.app/` | → **200** (`pai-skills` worker) | 🟢 LIVE |
| Gspace | `https://gspace.axiomid.app` | → **200** (Vercel prod, `PAI-Gspace`) | 🟢 LIVE |
| Learn academy | `https://learn.axiomid.app/` | → **200** (tracks + Earn⇄Learn loop) | 🟢 LIVE |
| Earn exchange | `https://earn.axiomid.app/` | → **200** (portal; escrow not yet wired) | 🟢 LIVE |
| Node port | `https://node.axiomid.app/` | → **200** | 🟢 LIVE |
| Auth portal | `https://auth.axiomid.app/` | → **200** (Pi SDK auth pending) | 🟢 LIVE |
| Memory | `https://memory.axiomid.app/` | → **200** (portal; L2/L3 engines Phase-2) | 🟢 LIVE |
| PiVerify (KYA) | `https://piverify.axiomid.app` | → **200** `{"service":"axiomid-piverify"}` | 🟢 LIVE |
| — aip · ppp · mail · harness · index · jobs · rewards · ads | `*.axiomid.app` | each → **200** (route-mapped portals) | 🟢 LIVE |
| OG image API | `https://axiomid.app/api/og` | worker→Vercel proxy (see note \*) | 🟡 PARTIAL |

\* **OG note:** the apex is a worker, so `/api/og` proxies to the AxiomID Next.js app on Vercel; that Vercel deployment currently returns `403 Invalid host` on its preview host — Vercel deployment-protection/alias fix is the open item.

## 🔴 Not live (explicitly)

| Service | State | Proof |
|---------|-------|-------|
| `api.axiomid.app` | **NXDOMAIN** — not deployed | `curl -s --max-time 8 https://api.axiomid.app/health` → `000` |
| `pai.build` / `docs.pai.build` | NXDOMAIN (marketing/docs not published yet) | — |
| Identity Next.js app | Vercel build green, **no public domain** (403 on direct alias) | not user-facing yet |

> History: `clawhub.*`/`clawhub`/`clawhub-ar` repos were **deleted** 2026-08-07 (cleanup documented in vault `05-Layers/L7-Skills.md`); `hermes-*` and 4 repos are archived. Nothing that was deleted is listed as live.

## 🧭 Repository Map (GitHub API 2026-08-08)

**Active (23):** `.github` · AxiomID · protocol-stubs · pai-skills · PAI-Gspace · pai-website · pai-docs · pai-mcp · pai-gateways · pai-api-gateway · pai-agent-kit · PAI-Memory · PAI-Protocol · ADP · openidentity · openidentity.md · axiomid-piverify · pai-atom · pai-cli · pai-core · pai-tools · PAI-Email-Agent · PiWorker

**Archived (4):** `pai-port` · `pai-sam` · `ppm` · `skillbuilder` (functionality merged into `pai-tools`)

## 🏛️ Architecture (as actually running)

```
Edge (Cloudflare Workers)   hub + 15 portal subdomains + CaaS + SEO/OG + sitemap   → LIVE
L1 Identity                  AxiomID (Next.js 15, Vercel) — i18n EN/AR/ZH/HI + PostHog wired; public domain pending
L2 Runtime / L3 memory       pai-agent-kit · PAI-Memory      → portals live, engines Phase-2
L4 Protocol                  PAI-Protocol · ADP · pai-mcp   → spec repos; live stubs on edge
L7 Market                    pai-skills (live 4-lang registry — 4GET) · earn portal
```

Honesty label: **portal live = page served edge-first; token/escrow/agent execution is NOT claimed live anywhere.**

## 🔍 Re-verify in one command

```bash
for u in axiomid.app skills.axiomid.app gspace.axiomid.app learn.axiomid.app earn.axiomid.app node.axiomid.app memory.axiomid.app auth.axiomid.app piverify.axiomid.app; do
  printf "%-26s %s\n" "$u" "$(curl -s -o /dev/null -w '%{http_code}' --max-time 8 https://$u)"
done
curl -s https://axiomid.app/.well-known/mcp.json -H "Accept: application/mcp+json"
```