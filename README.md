# ARTHACK — Dungeon Escape

**ARTHACK** is a browser roguelike where a medieval dungeon and a corporate intrusion job are the same contract. Guards carry poleaxes; doors run SSH. You are Guild muscle with a portable rig, orders to climb out of the **Black Keep**, and — if you survive that — a second job nobody briefed you on.

**Play online:** [https://artofscripting.github.io/ArtHackWeb/arthack.html](https://artofscripting.github.io/ArtHackWeb/arthack.html)

Or open `arthack.html` locally in any modern browser. No install, no server. Pick an operative and difficulty, read the briefing, descend.

| Platform | Controls |
|----------|----------|
| Desktop | Move with arrows / WASD / `hjkl`. Press `?` in-game for full help. |
| Mobile | Enable touch mode (corner link). Swipe to move; action bar for search, hack, fight, inventory. |

---

## The setting

The Black Keep never finished modernizing. Barons swear on steel; seneschals swear on CastleNet. Deep strata jam radio and swallow signal, so contractors carry blades **and** exploit kits.

You are **ARTHACK** — operative, thief, netrunner, whichever archetype you chose. The first contract is simple: climb procedurally generated floors (oubliettes, barracks, throne antechambers) and reach the **surface gate** (`>`).

Breaching the gate triggers **Act 2**. Handlers on the rampart explain that extraction is not over:

1. The gate is welded shut behind you.
2. You re-enter via the **West Sally Port** on a **fresh dungeon layout**.
3. You descend again to find **three charter fragments** (`*`).
4. You arm the **portal** (`O`) and step through to go home.

Clues and the portal exist only in the return act. Throughout both acts, **story strain** rises — climbing during escape, collecting clues during return — and the keep answers with tougher foes and richer loot.

---

## What a run feels like

ARTHACK is **turn-based**. Each step, swing, search, or hack advances time; enemies move after you. You explore fog-of-war dungeons room by room, opening doors, looting caches, fighting or sneaking past hostiles, and rooting terminals when the map demands it.

Three pressures run in parallel:

- **Survival** — HP, armor, potions, stealth, and whether you fight in the open or from shoot mode with a bow.
- **Heat** — noise from combat and hacking. High heat brings reinforcements and a SOC responder that hunts terminals you have rooted.
- **Economy** — creds from kills, contracts, botnet ticks, and sold loot; spent at quartermasters (`%`) on gear, modules, gems, and rig parts.

Optional **contracts** each run pay extra for rooting terminals, crafting modules, or planting C2 nodes.

### Map symbols

| | | |
|---|---|---|
| `@` you | `<` stairs down | `>` surface gate |
| `!` terminal | `$` loot cache | `*` clue (return act) |
| `O` portal | `%` shop | `k` key |
| `A` anvil | `F` craft table | `#` `+` wall / door |

Unidentified loot appears as `$` until you pick it up; quality depends on source, depth, personality stats, and your build.

---

## Staying alive

Combat is bump-to-attack melee or **ranged** fire after equipping a bow, crossbow, or slingshot (`z` toggles shoot mode). **Stealth** (`v`) quiets your movement. Stats come from weapons, armor (head / chest / legs), shield, jewelry, and **combat gems** socketed at an anvil.

**Potions** span seven families (heal, neural, chill, sight, vigor, ward, fury) with multiple named tiers each. Kills pay creds that scale with depth and story strain; some enemies drop loot or unlock hack modules.

Clearing all visible hostiles can zero out heat — useful before a loud hack.

---

## Owning CastleNet

Terminals (`!`) are doors, vaults, cameras, radios, and servers. Each has open ports, log files, fake credentials, and vulnerabilities styled after real CVE workflows.

Typical intrusion path:

1. **Scan** the area (`scan`, or interact from the map).
2. **Port scan** and **vuln scan** to see services and which tools you lack.
3. **Hack** with a module loadout — or **instant root** if you already extracted that host's secret.
4. After root: browse the shell, pull secrets, install **botnet** nodes, **pivot** elsewhere, **clear logs**, **practice** skills on the box.

Use `t` / `/` for quick commands or `term` for a full SSH-style shell. Optional **minigames** after scans and hacks award bonus creds, heat relief, or loot. Double-tap a rooted terminal to queue the next shell command quickly.

**Modules** (crafted, bought, or looted) unlock **tools** — port scan, exploit, credential dump, kerberoast, pivot relay, and dozens more mapped to a MITRE-flavored toolkit (`p`). Missing tools block the hack until you fill the gap.

Your **portable console rig** (`0`) matters here: eight slots (chassis, keyboard, screen, CPU, GPU, NIC, storage, cooler) each hold parts that add hack skills and personality stats. If rig tier falls behind story strain, hacks start failing until you upgrade.

---

## Getting stronger

### Equipment and gems

Inventory covers weapons, armor, backpacks, rings, amulets, materials, modules, and potions. Backpacks set carry weight and pack capacity. Items are color-coded by **rarity**; sell and buy prices scale with rarity, quality, and how deep you are in the run.

At an **anvil** (`A`), socket gems into almost anything:

- **Combat gems** (`^`) — attack, defense, sight, carry, hack bonuses.
- **Personality gems** (`♦`) — luck, charm, wit, nerve (active when the host item is equipped or the rig part installed).

### Crafting (`g`)

- **Craft table** (`F`) — forge weapons, armor, potions, and entry-level modules from wood, metal, clay, and salvaged electronics.
- **Anvil** — metalwork recipes plus the socket UI.

### Shops and loot

Quartermasters stock dozens of items: gear, jewelry, potions, both gem types, console parts, modules, and cred stashes. Stock shuffles and restocks over time.

Loot stubs spawn from floors, chests, enemy drops, hacked caches, and vaults. Premium sources (locked hack chests, vaults) skew toward better rolls. **Luck, charm, wit, and nerve** — from archetype, rig parts, and socketed gems — feed directly into those rolls.

---

## Choosing an operative

Sixteen **archetypes** reshape each run: starting modules, creds, personality, skill bias, and a passive trick.

| Archetype | Angle |
|-----------|-------|
| Infiltrator | Stealth, fast alert decay |
| Combat Specialist | Melee damage, bonus kill coin |
| Netrunner | Terminal awareness, core hack modules |
| Ghost Operator | Social hacks, charm |
| Vault Raider | Loot quality on chests and caches |
| Pivot Architect | Lateral movement, pivot success |
| Cipher Breaker | Kerberos / NTLM / bruteforce |
| Signal Phantom | RF spoofing, evasion, cameras |
| Data Broker | Credential harvesting, charm-weighted loot |
| Breach Striker | Exploits plus door-kicking |
| Archivist | Recon, extra clue chance (return act) |
| Clean Slate | Log wiping, heat management |
| Field Surgeon | HP and potion efficiency |
| Deadeye | Ranged focus |
| Rootkit Smith | Persistence and exploit tooling |
| Fortune Runner | Luck-heavy economy |

**Skills** (`u`) — recon, exploit, creds, lateral, persist, evasion, melee, ranged, social — improve through practice on rooted terminals and successful operations.

---

## Between runs

Beat the portal and the game saves to `localStorage`. Up to **six modules** carry into the next attempt. Difficulty (easy / normal / hard / nightmare) changes enemy scaling and briefing tone.

---

## Controls (quick reference)

| Key | Action |
|-----|--------|
| Move | Arrows, WASD, `hjkl` |
| `l` | Look |
| `e` / Space | Search |
| `A` | Auto-loot room |
| `i` | Inventory |
| `g` | Craft / socket |
| `p` | Toolkit |
| `0` | Console rig |
| `x` | Hack |
| `t` / `/` | Commands |
| `term` | Shell on adjacent `!` |
| `v` / `z` | Stealth / shoot |
| `m` | Minimap |
| `n` / `8` | Journal / secrets |
| `o` / `=` | Log / summary |
| `?` / `c` | Help / full command list |
| `r` | Rest |
| `q` | Quit |

Typed commands include `equip`, `drink`, `buy`, `sell`, `scan`, `portscan`, `vulnscan`, `hack`, `botnet`, `pivot`, `clearlogs`, and `difficulty`. The in-game `c` overlay lists everything valid in context.

---

## Technical notes

- **Single file:** `arthack.html` (~8600 lines), canvas-rendered, zero dependencies.
- Responsive layout with portrait sidebar and touch UI.
- Ported from a multi-stage Python roguelike reference (stages 1–7 annotated in the source header).
