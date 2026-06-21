# Corvid

DETAILED USER GUIDE HERE (Updated June 21, 2026): https://docs.google.com/document/d/1-BAMu7jq-UagDj6RpzpgcCeEyv__dQCOO2fUP25nzm0/edit?usp=sharing 

```
   (oVo)
  // ^ \\
C O R V I D
Thought and memory, with wings.
```

A persistent, session-aware hacking toolkit for [Grey Hack](https://store.steampowered.com/app/605230/Grey_Hack/). Corvid replaces the game's default terminal with a unified command shell that accumulates intelligence across sessions, automates exploit workflows, manages bounce networks, and tracks everything you discover.

> All targets, credentials, exploits, and operations exist solely within the Grey Hack game environment.

> **Early release:** Corvid is freshly released and while it has been tested, bugs may surface during normal play. If you encounter an issue please report it on the [GitHub issues page](../../issues) with a description of what you were doing and any error messages shown.

---

## What it does

- **Remembers everything** — persistent databases for targets, credentials, persons, organisations, and an exploit knowledge base that grows across sessions
- **Automates attacks** — full recon → exploit → harvest → pivot pipeline with a single command
- **Manages your infrastructure** — bounce chains, reverse shell nodes (flock/roost), and platform attack via remote nodes so your Nest never appears in target logs
- **Scores libraries** — identifies high-value exploit libraries on compromised machines and helps you collect and deploy them strategically
- **Cracks passwords** — integrated Chainsaw cracker (Markov chain + wordlist) fires automatically during escalation

A full command reference and operational guide is available in the [Corvid Handbook].
https://docs.google.com/document/d/1-BAMu7jq-UagDj6RpzpgcCeEyv__dQCOO2fUP25nzm0/edit?usp=sharing 

---

## Installation

1. Copy the `corvid_installer/` contents to your Nest (e.g. `/root/corvidinstaller/`)
2. Run `installer0.src` through `installer7.src` in order — open each in Code Editor, Save, Build, Run
3. Copy the `tools/` folder to `/Corvid/tools/` via FileExplorer
4. Launch Corvid and build the tool binaries:

```
/Corvid/corvid
platform build
chainsaw build
```

Port 1222 must be forwarded on your Nest router for flock/roost to work.

---

## Quick start

```
attack 1.2.3.4          full guided attack on a target
bounces chain 3         route through 3 bounce hops
shinylibs get           collect high-value exploit libs from current session
dbstats                 see everything Corvid has recorded
leave                   return to Nest
```

---

## Credits & Acknowledgements

**Author:** PurpleBird

**Chainsaw** — the integrated password cracker is [ChainSaw](https://github.com/jwfraustro/chainsaw/) by NitroCynic, a Markov chain password cracker released under the MIT licence and ported to GreyScript for use in Corvid.

**Inspiration and community:**

- **Viper** — the dominant community hacking tool, whose feature set helped define what a Grey Hack toolkit should cover
- **Crowsploit** — architectural patterns including the ZeroDaySolver exploit text parser, the `sanity_check` facade pattern, and per-session metaxploit handling
- **Lunarium / FoxLib** — the LibFinder filesystem walking pattern for lib discovery
- **CelestialCorp Unity** — LINQ-style list predicate patterns (`where`, `first`, `wherenot`) that informed Corvid's DB query design
- **5hell** and **N-Vision** — community tools that demonstrated what's possible in GreyScript

**Grey Hack Discord community** — particularly **Clover** (whose sudo escalation technique is the backbone of Corvid's Clover Method), **Nyx** (who confirmed how `connect_service` routes traffic, which shaped the entire opsec model), and **Manzana** for general GreyScript mechanic knowledge. Without community knowledge-sharing this project would not exist.

---

## Licence

MIT
