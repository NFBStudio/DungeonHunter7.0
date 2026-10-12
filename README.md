# Dungeon Hunter — 7.0 Ultimate

A modular, GitHub Pages-compatible dark-fantasy roguelite RPG. No build step is required.

## Core game
- Up to 1,000-room descent plus Ascension/endgame scaling
- Multiple classes: Ranged Hunter, Melee Hunter, Priest
- Procedural rooms, biomes, elite modifiers, hazards, caches and room challenges
- Extraction economy with permanent progression and banked gear
- Large equipment system with rarity, affixes, set/relic-style build choices, forge and shop systems
- Hunter Path, attributes, skills, starting upgrades and temporary expedition upgrades
- Daily trials, achievements, leaderboard integration and persistent save data

## 6.2 Contract & Boss systems
- Six deterministic daily contracts with Bronze → Mythic tiers
- Hunt, elite, boss, named-boss bounty, treasure, depth and speed contracts
- Contract streak rewards and faction reputation
- Five named boss identities plus Ascendant versions
- Boss codex telemetry and named boss HUD

## 6.3 Ultimate expansion
- **Weekly Hunts** with rotating objectives and two rerolls per week
- **Faction Ranks** from Outsider → Paragon with reputation-based reward multipliers
- **Achievement milestones** covering kills, elites, bosses, depth, clean boss rooms and rare loot
- **Boss-exclusive relic drops** tied to each named boss; Ascendant bosses can upgrade them to Godly
- **Room Mutations** that alter enemy stats and room rules: Blood Moon, Hollow Fog, Treasure Surge, Predator’s Law, Arcane Flux, Iron Trial and Quiet Depths
- **Clean-boss tracking** for untouched boss-room clears
- Fixed treasure-contract tracking so opened caches count as caches rather than bounty kills
- Contract event telemetry (`contract:accepted`, `contract:completed`) for future UI/analytics extensions

## 7.0 Buildcraft & combat overhaul
- **Eight gear sets** with 2/4/6-piece bonuses that reward deliberate equipment builds.
- **Rarity-based affixes** from Uncommon through Godly, with permanent item stats stored directly on gear.
- **The Forge**: craft Rare gear, enchant selected items and masterwork equipment up to +10.
- **Forge materials** drop from monsters, elites and bosses, creating a second progression loop alongside gold.
- **Room variants** including Bloodmoon, Sanctum, Cursed Vault, Hunter’s Gambit, Treasure Vault and Echoing Halls.
- **Hunter’s Gambit** creates an explicit risk/reward decision before the room unfolds.
- **Boss phase system** changes boss speed, damage and signature attacks at 66% and 33% HP.
- **Combat combo layer** rewards uninterrupted kill streaks with bonus gold and feeds the Forge economy.
- **Forge HUD + boss phase feedback** make major combat states visible without adding a heavy framework.

## Architecture
```text
js/
  content/       stable content registries and named bosses
  core/          engine, event bus, lifecycle, performance, ultimate layers
  entities/      inventory/equipment logic
  rendering/     canvas rendering and effects
  systems/       dungeon, combat, progression, contracts, boss systems
  ui/            lodge and interface rendering
```

The expansion layer is intentionally additive: the existing combat/dungeon core remains usable while higher-level systems subscribe to lifecycle events.

## GitHub Pages
Upload the contents of this folder to a repository and enable GitHub Pages. All game assets use relative paths and there is no server-side build requirement.

## Validation
- All JavaScript files pass `node --check`.
- Concatenated JavaScript passes `node --check`.
- All local `<script>` and `<link>` references resolve.
