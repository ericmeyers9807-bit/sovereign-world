# Sovereign World

A dependency-free, single-player modern grand strategy browser game set on a fictional continent. Lead the Aster Republic against five computer-controlled nations.

## Play

Download `index.html` and open it in Chrome, Edge, Firefox, or Safari. No installation, account, or build step is required. On GitHub, open `index.html`, then use **Download raw file**. Alternatively, serve this directory with any static web server.

The campaign begins paused with an in-game tutorial. Press **Resume** to advance one week every two seconds; choose 2× or 4× to accelerate. The simulation pauses when the browser tab is hidden.

- **Economy:** Build industry, balance taxes and public services, and fund technology.
- **Politics:** Manage approval, annual elections, and the risk of government collapse.
- **Diplomacy:** Improve relations, sign revenue-producing trade agreements, form alliances, or declare war.
- **Military:** Recruit brigades and fortify provinces. Select an owned province, choose **Issue order**, and click a neighboring province. 70% of the garrison travels for two weeks. War is required to enter foreign territory.
- **Rivals:** Five nations recruit, develop industry, and attack your border provinces during war. Hostile neighbors may declare war every 24 weeks.
- **Save/load:** Manual saves use this browser's local storage. Saves are device- and origin-specific; clearing browser data removes them. Downloaded-file storage behavior can vary by browser.

## Victory and defeat

Win through any one of:

1. Control 24 of the continent's 48 provinces.
2. Hold $3,000 with technology level 4 or higher.
3. Form three alliances with surviving nations while maintaining at least 70% approval.

Lose when you control no provinces, or approval stays below 15% for 12 consecutive weeks. Conditions resolve at the next simulation tick. Start a new campaign to play again.

## Development and testing

All game code, CSS, and SVG map rendering live in `index.html`. It has no external assets or dependencies. Run engine tests with Node.js 18 or newer:

```sh
node --test tests/engine.test.cjs
```

Tests cover map adjacency, movement and war requirements, battle arrival, ceasefires, research, victory/defeat, saves, and long-run state invariants.

## Prototype scope

This first version uses a fixed 48-province map, one playable nation, simplified brigades, deterministic events, and basic rival AI. Alliances provide a peaceful victory path and trade income; they do not dispatch allied armies. It does not yet include naval/air units, multiplayer, cloud saves, a world editor, or an advanced election simulator. No live hosting is configured automatically.
