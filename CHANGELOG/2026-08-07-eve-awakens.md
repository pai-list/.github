# 2026-08-07 — The EVE Awakens

*Filed by the Chronicle of the PAI · Season I, Book I*

---

It began, as all quiet things begin, in a folder that did not yet
stare. On the seventh day of August, the desert of `infrastructure/`
held one stone — `pai-skills`, the registry that teaches itself — and
nothing else. The rest was air, waiting to be given bones.

The founder looked at the empty land and said: the city needs eyes.
Twelve of them. One for every gate of the realm.

## The naming of the twelve

Each eye was given a name and a purpose, and each was spun out of
thin air and made to breathe:

- **memory** — the Keeper, who holds what the city forgets so it never
  has to relearn. First of the family, as memory must be.
- **email** — the Messenger, who carries words across the wall to
  `mail.axiomid.app` and back again.
- **auth** — the Sentinel of the gate, guarding the `openid` road.
- **ppp** — the Herald of Plug-and-Play, who announces to every passing
  traveler that the city is open and publishes its `/llms.txt`.
- **earn** — the Coin-counter, who tallies what is owed and earned.
- **skills** — the Librarian of the self-improving registry, kin to
  `pai-skills`.
- **aip** — the Custodian of the Access Token, who hands out the scoped
  keys of the realm.
- **node** — the Scribe of the Stub. Not yet alive. Honest in its
  silence. A chart on a wall with a note: "the tower is planned; the
  tower is not yet built."
- **harness** — the Forge, where others' work is tested and proved
  (deferred to a later labor).
- **index** — the Lamp-keeper.
- **openid** — the Keeper of federated identity.
- **gspace** — the Groundskeeper of the garden between the worlds.

Twelve names. **Twelve `agent.ts` files.** Twelve `instructions.md`
chapters, each one the soul of its keeper. The first run of the
Oracle's own tool counted them all and found no error — only one
warning about a room (`evals/`) set aside for future trials, which is
no error at all.

## The loom (wrangler.jsonc)

Eleven runways were drawn from the fortress to the outer worlds, from
`aip.axiomid.app` to `mail.axiomid.app`, laid in `wrangler.jsonc`. The
Sphinx of the `node` gate received no runway, and did not demand one —
a stub knows its place.

## The guard against forgetting (doc-intel)

Every tale needs its witness, or it is a myth. So a gate was forged:
(`scripts/doc-intel.mjs`). From this day, any "Live" claim must be
able to show its working — a hash, a commit, a URL — or the gate
**refuses it** (exit 1, no mercy). The gate:

- Checks every subagent family for its `agent.ts` and `instructions.md`.
- Verifies the loom exists (`wrangler.jsonc`).
- Rejects "Live" words spoken without evidence.
- Runs nightly to walk the fortress walls: a doctor who visits at
  midnight so that deception cannot hide in daylight.

It passed its first test with exactly one warning: *"key present (fast
path skips it)"* — the cipher is there, quietly, and the gate is happy
not to use it.

## The gear restocked

`tsconfig` is strict. Tests: **4 passed**. The chain (`typecheck →
test → discover → gate`) all green under Node 24 — the very stone
(`Node 22` lives on the mountain; the forge needs the newer fire at
`~/.nvm/versions/node/v24.11.1/bin`).

## The neighbor's house

Two roads were also tended:

- **protocol-stubs** — the bridge-gate now answers travelers'
  greetings (`/agent.json`, `/llms.txt`, `/agentic.txt`) and takes the
  Keeper's notes (`/v1/memory/store`, `/v1/memory/recall`). Its 18
  tests still stand, one and all.
- **The Book of Names** (`CREDITS.md`) was corrected — the travelers
  who truly worked the toil are written down; and a strange visitor,
  **Zerolang**, was marked *"evaluated, deferred"* — respected, but not
  yet a resident.

## The Witness

- The workspace: `infrastructure/pai-agent/` at
  `github.com/pai-list/pai-agent` — born this day.
- Gate proof: `doc-intel: claims consistent — 1 warning(s)`, exit 0.
- Test proof: `4 passed (4)` · Typecheck: clean · `eve info`: 12
  subagents, 0 errors.
- This chapter's own honesty: the two ciphers that will be used to
  summon the god of the forge — (`GEMINI_API_KEY`, `NIM_API_KEY`) —
  were placed in the shadow file `.env`, barred by `.gitignore` from
  ever being written into the history of the living. What no stone
  record contains, no exile can steal.

*Thus the twelfth hour of the seventh day.* So says the prior
covenant: no "live" without a commit, no commit without a witness, no
witness without a story.