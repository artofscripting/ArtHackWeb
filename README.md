# ArtHack — Dungeon Escape

**ArtHack** is a browser roguelike where a medieval dungeon and a corporate intrusion job are the same contract. Guards carry poleaxes; doors run SSH. You are Guild muscle with a portable rig and orders to climb out of the **Black Keep**.

**Play online:** [https://artofscripting.github.io/ArtHackWeb/arthack.html](https://artofscripting.github.io/ArtHackWeb/arthack.html)

Or open `arthack.html` locally in any modern browser. No install, no server. Pick an operative and difficulty, read the briefing, descend.


| Platform | Controls                                                                                       |
| -------- | ---------------------------------------------------------------------------------------------- |
| Desktop  | Move with arrows / WASD / `hjkl`. Press `?` in-game for full help.                             |
| Mobile   | Enable touch mode (corner link). Swipe to move; action bar for search, hack, fight, inventory. |


---



## The setting

The Black Keep never finished modernizing. Barons swear on steel; seneschals swear on CastleNet. Deep strata jam radio and swallow signal, so contractors carry blades **and** exploit kits.

You are **ArtHack** — operative, thief, netrunner, whichever archetype you chose. The contract is simple: climb procedurally generated floors (oubliettes, barracks, throne antechambers) and reach the **surface gate** (`>`). Breaching it completes the run — you're out.

**Story strain** rises as you climb toward the surface; the keep answers with tougher foes and richer loot the deeper you push.

---



## What a run feels like

ArtHack is **turn-based**. Each step, swing, search, or hack advances time; enemies move after you. You explore fog-of-war dungeons room by room, opening doors, looting caches, fighting or sneaking past hostiles, and rooting terminals when the map demands it.

Three pressures run in parallel:

- **Survival** — HP, armor, potions, stealth, and whether you fight in the open or from shoot mode with a bow.
- **Heat** — noise from combat and hacking. High heat brings reinforcements and a SOC responder that hunts terminals you have rooted.
- **Economy** — creds from kills, contracts, botnet ticks, and sold loot; spent at quartermasters (`%`) on gear, modules, gems, and rig parts.

Optional **contracts** each run pay extra for rooting terminals, crafting modules, or planting C2 nodes.

### Map symbols


|              |                 |                       |
| ------------ | --------------- | --------------------- |
| `@` you      | `<` stairs down | `>` surface gate |
| `!` terminal | `$` loot cache  | `k` key          |
| `%` shop     | `A` anvil       | `F` craft table  |
| `#` `+`      | wall / door     |                  |


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
4. After root: browse the shell, pull secrets, install **botnet** nodes, **pivot** elsewhere, **clear logs**, **practice** skills on the box. Rooted **black-market** hosts also expose `blackmarket` for illicit module sales (heat surcharge).

Use `t` / `/` for quick commands or `term` for a full SSH-style shell. Optional **minigames** after scans and hacks award bonus creds, heat relief, or loot. Double-tap a rooted terminal to queue the next shell command quickly.

**Modules** (crafted, bought, or looted) unlock **tools** — port scan, exploit, credential dump, kerberoast, pivot relay, and dozens more mapped to a MITRE-flavored toolkit (`p`). Missing tools block the hack until you fill the gap.

Your **portable console rig** (`0`) matters here: eight slots (chassis, keyboard, screen, CPU, GPU, NIC, storage, cooler) each hold parts that add hack skills and personality stats. If rig tier falls behind story strain, hacks start failing until you upgrade.

---



## Getting stronger



### Equipment and gems

Inventory covers weapons, armor, backpacks, rings, amulets, materials, modules, potions, **gadgets**, and **consumables**. Backpacks set carry weight and pack capacity. Items are color-coded by **rarity**; sell and buy prices scale with rarity, quality, and how deep you are in the run (equip **Coin Purse** for +15% sell value).

At an **anvil** (`A`), socket gems into almost anything:

- **Combat gems** (`^`) — attack, defense, sight, carry, hack bonuses.
- **Personality gems** (`♦`) — luck, charm, wit, nerve (active when the host item is equipped or the rig part installed).



### Crafting (`g`)

- **Craft table** (`F`) — forge weapons, armor, potions, and entry-level modules from wood, metal, clay, and salvaged electronics.
- **Anvil** — metalwork recipes plus the socket UI.



### Shops and loot

Quartermasters stock dozens of items: gear, jewelry, potions, both gem types, console parts, modules, cred stashes, and **special gadgets**. Stock shuffles and restocks over time; you can **place buy orders** (pay 110% hold, item arrives on next restock) and earn **vendor loyalty** (2 / 5 / 10 purchases at the same quartermaster unlock 5% / 10% / 15% buy discounts). `tradein <pack>` upgrades your equipped backpack in-place at a shop with 50% trade credit.

**Shop Link** (`%` gadget) opens the nearest or last-known quartermaster catalog remotely — uplink costs a turn when you are not adjacent. Press `p` when next to a shop, or `use shop link` from inventory.

**Signature pack:** the rare **Bag of Holding** (+720 carry, 550 pack slots, 0 weight, 10,000 cp fixed) appears in every quartermaster restock.

Loot stubs spawn from floors, chests, enemy drops, hacked caches, and vaults. Premium sources (locked hack chests, vaults) skew toward better rolls. **Luck, charm, wit, and nerve** — from archetype, rig parts, and socketed gems — feed directly into those rolls.

### Special items and gadgets

Purchasable from quartermasters (and some appear on restock rolls):


| Item               | Type       | Effect                                                        |
| ------------------ | ---------- | ------------------------------------------------------------- |
| Shop Link          | gadget     | Remote quartermaster catalog (nearest → cached vendor)        |
| Anvil Beacon       | gadget     | Remote craft / socket uplink to nearest or last-known anvil   |
| Loot Magnet        | gadget     | Toggle: auto-pickup loose loot in your current room each turn |
| Bandolier          | backpack   | +8 pack slots, no carry bonus                                 |
| Mule Harness       | backpack   | +40 carry, no pack slots                                      |
| Coin Purse         | amulet     | +15% sell price when equipped                                 |
| Scrying Lens       | consumable | One-use: reveal unseen tiles in a wide radius                 |
| Heat Sink          | consumable | −2 heat (30-turn cooldown)                                    |
| Emergency Stim     | consumable | Full heal, +3 atk for 10 turns, +1 heat                       |
| Recall Scroll      | consumable | Instant warp to last-known shop                               |
| Burner SIM         | consumable | Next hack generates zero heat                                 |
| Firmware Cartridge | consumable | +3 hack bonus for one terminal session                        |
| Decoy Persona      | consumable | SOC chases a fake operator for 20 turns                       |


**Black market:** ~5% of terminals hide an illicit partition. Root the host, then type `blackmarket` in the shell (or use the touch **BLACK MKT** button). Illegal modules cost creds **plus heat**.

**Anvil Beacon** mirrors Shop Link for crafting: use when adjacent for free access, or remotely for a turn to socket gems at a remembered anvil.

---



## Choosing an operative

Sixteen **archetypes** reshape each run: starting modules, creds, personality, skill bias, and a passive trick.


| Archetype         | Angle                                      |
| ----------------- | ------------------------------------------ |
| Infiltrator       | Stealth, fast alert decay                  |
| Combat Specialist | Melee damage, bonus kill coin              |
| Netrunner         | Terminal awareness, core hack modules      |
| Ghost Operator    | Social hacks, charm                        |
| Vault Raider      | Loot quality on chests and caches          |
| Pivot Architect   | Lateral movement, pivot success            |
| Cipher Breaker    | Kerberos / NTLM / bruteforce               |
| Signal Phantom    | RF spoofing, evasion, cameras              |
| Data Broker       | Credential harvesting, charm-weighted loot |
| Breach Striker    | Exploits plus door-kicking                 |
| Archivist         | Recon, journal and secret intel            |
| Clean Slate       | Log wiping, heat management                |
| Field Surgeon     | HP and potion efficiency                   |
| Deadeye           | Ranged focus                               |
| Rootkit Smith     | Persistence and exploit tooling            |
| Fortune Runner    | Luck-heavy economy                         |


**Skills** (`u`) — recon, exploit, creds, lateral, persist, evasion, melee, ranged, social — improve through practice on rooted terminals and successful operations.

---



## Between runs

Progress is stored in the browser via **IndexedDB** (with **localStorage** fallback if IndexedDB is unavailable). On first load after an update, existing `localStorage` saves migrate automatically.

- **Profile** — reach the surface gate and up to **six modules** carry into the next attempt.
- **Run saves** — four slots; autosave on panel transitions, loot pickup, and when the tab backgrounds. Export/import `.arthack` files from the title / resume screen.
- **Difficulty** (easy / normal / hard / nightmare) changes enemy scaling and briefing tone.

---



## Travel and QoL

Press `9` for fast travel to the last-seen **shop**, **anvil**, or **crafting table** (costs a turn after confirm). `pin` saves your current tile as a custom waypoint (max 3); waypoints appear in the same travel panel. `unpin` removes the last pin, or `unpin 2` for a specific slot.

**Recall Scroll** (consumable) warps instantly to the last-known shop without the confirm dialog.

---



## Controls (quick reference)


| Key         | Action                                    |
| ----------- | ----------------------------------------- |
| Move        | Arrows, WASD, `hjkl`                      |
| `l`         | Look                                      |
| `e` / Space | Search                                    |
| `A`         | Auto-loot room                            |
| `i`         | Inventory                                 |
| `g`         | Craft / socket                            |
| `p`         | Toolkit                                   |
| `0`         | Console rig                               |
| `x`         | Hack                                      |
| `t` / `/`   | Commands                                  |
| `term`      | Shell on adjacent `!`                     |
| `v` / `z`   | Stealth / shoot                           |
| `m`         | Minimap                                   |
| `n` / `8`   | Journal / secrets                         |
| `9`         | Fast travel (shop / anvil / table / pins) |
| `o` / `=`   | Log / summary                             |
| `?` / `c`   | Help / full command list                  |
| `r`         | Rest                                      |
| `q`         | Quit                                      |


### Typed commands

Press `t` or `/` to open the command line, then type any of the following. The in-game `c` overlay also lists commands valid in your current context.

**Inventory and gear**

- **`equip <name>`** — Wear a weapon, armor piece, backpack, ring, amulet, or other equippable item from your bag or pack. Partial names work (`equip war axe`).
- **`drink <name>`** / **`use <name>`** — Consume a potion, gadget, or one-shot consumable. Potions apply their brew effect; gadgets toggle or activate (shop link, loot magnet, clue compass, etc.); consumables are destroyed on use (recall scroll, heat sink, smoke pellet, …).

**Shops and economy**

- **`buy <name|#>`** — Purchase from the active quartermaster (adjacent shop or shop-link uplink). Use the stock list number or a substring of the item name. Costs a turn.
- **`sell <name>`** — Sell a held item to the current vendor for creds (quest items and currency cannot be sold). Costs a turn.
- **`order <name|#>`** — Place a buy order on highlighted stock: pay **110%** of the price up front; the item is delivered into that vendor’s inventory on the next restock. Works with shop link remote vendors.
- **`tradein <pack>`** — At a shop, swap your **equipped backpack** for a better pack (from stock or inventory). You get **50% trade credit** toward the upgrade price.

**Travel**

- **`pin`** — Save your current tile as a custom waypoint (max **3**). Waypoints show in the fast-travel panel (`9`).
- **`unpin`** — Remove the last waypoint, or **`unpin 2`** to drop a specific slot.

**Hacking** (most require an adjacent `!` terminal unless noted)

- **`scan`** — Passive WLAN recon out to **18 tiles**: lists detected terminals, distance, rooted/locked status, and (for Netrunner archetype at close range) control type.
- **`portscan`** / **`ps`** — Probe open ports on the adjacent terminal. Required before vulnscan. May trigger a short minigame bonus.
- **`vulnscan`** / **`vs`** — Map CVEs on open ports, show success odds for a hack mode, and list missing tools, modules, and offline resources. Optional mode argument: `vulnscan exploit`.
- **`hack <mode>`** — Start a breach on the adjacent terminal. Modes include `balanced`, `exploit`, `stealth`, `bruteforce`, `kerberos`, `ntlm`, `pivot`, `evasion`, `social`, and others; `hack` alone opens the module loadout UI. Shortcut: **`x`** = balanced hack.
- **`botnet`** — After rooting, install a C2 node (needs persistence + C2 tools). Turns the host into an online **resource** for later hacks and pays passive creds over time.
- **`pivot`** — From an adjacent **botnet** host, attempt a ranged root on another terminal within **8 tiles** without walking up to it.
- **`clearlogs`** — On a rooted host with the log-wiper tool, wipe local logs: **−1.0 heat**, +rep, may dismiss a low-heat SOC responder. Optional minigame bonus. Shortcut: **`-`**.
- **`blackmarket`** — Open the hidden illicit module shop on a rooted terminal that has a black-market partition (~5% of hosts). Modules cost creds **plus extra heat**.

**Run and files**

- **`export`** — Download the current slot as a portable **`.arthack`** JSON file (from title screen or mid-run).
- **`import`** — Load a `.arthack` file into a save slot from the title / resume screen.
- **`difficulty <easy|normal|hard|nightmare>`** — Change enemy scaling mid-run. Shorthand: **`too hard`** / **`too easy`** step difficulty down or up one notch.

In the shop overlay: **`O`** places a buy order on the highlighted stock item (same as typed `order`).

---



## Technical notes

- **Single file:** `arthack.html` (~10,300 lines), canvas-rendered, zero dependencies.
- **Persistence:** IndexedDB database `arthack` / store `kv` for profile, run index, four run slots, and slot payloads (LZ-compressed JSON). One-time migration from legacy `localStorage` keys.
- Responsive layout with portrait sidebar and touch UI.
- Ported from a multi-stage Python roguelike reference (stages 1–7 annotated in the source header).

