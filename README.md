# FORTNITE COMMAND CENTRE

A **game pack** for [gamebrain](https://github.com/koozyapno1/gamebrain) — a
generic game intel assistant that answers questions about a game from a
knowledge base and can speak the answers aloud.

This pack teaches it about **Chapter 6 Season 3 - Galactic Battle**.

## Install

```bash
git clone https://github.com/koozyapno1/gamebrain.git
cd gamebrain

git clone https://github.com/koozyapno1/gamebrain-pack-fortnite.git packs/fortnite

echo "PACK_DIR=./packs/fortnite" >> .env

docker compose up -d
```

Or with plain Python:

```bash
export PACK_DIR=./packs/fortnite
python app.py
```

Full instructions: **[gamebrain INSTALL.md](https://github.com/koozyapno1/gamebrain/blob/main/docs/INSTALL.md)**

## What it knows

| Area | Detail |
|---|---|
| **Topics** | 8 researched topics — Chapter 6 Season 3, POIs, Lightsabers, Blasters, Proximity Warning System, Building, ... |
| **Tips** | 41 ordered, practical steps |
| **Videos** | 24 real YouTube guide videos, linked per topic |

Every topic has an ordered **tips** list that the assistant returns as
numbered steps, and a **videos** list of working guide links.

## Files

```
pack.json    the manifest - tools, prompt, UI copy, reference tabs
kb.json      the knowledge base - all the game facts
```

No code, no keys, no secrets. Content only.

## Try it

```bash
curl -s http://localhost:8095/health | python3 -m json.tool
curl -s http://localhost:8095/tools | python3 -m json.tool
curl -s -X POST http://localhost:8095/chat \
  -H 'Content-Type: application/json' \
  -d '{"message": "What is new in Chapter 6 Season 3?"}' | python3 -m json.tool
```

Look for `tools_used` in the response. If it is empty the model answered from
memory instead of using the pack.

## Credits and sources

The game facts were compiled from public reference sources:

- polygon.com/fortnite-guide
- arcader.org (Fortnite Chapter 6)

YouTube video links point to the original creators' channels. All game names,
locations and trademarks belong to their respective owners. This pack is an
unofficial community reference and is not affiliated with or endorsed by the
publisher.

## Licence

The pack's **code and manifest** are MIT (same as gamebrain). The **game facts
and video links** are community-sourced content — see `kb.json` → `sources`
for attribution.
