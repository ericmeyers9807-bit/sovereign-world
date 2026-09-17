# Sovereign World — Iron Dawn

An original, single-player WWII-era grand strategy prototype set in a fictional world. The campaign begins on **3 September 1939**, with the Aster Republic already at war with the Karsk Directorate. This replaces the earlier modern-day hex-map prototype.

## Play

Download **index.html** and open it in a current desktop browser. Everything is bundled into this one file: no installation, external assets, account, server, or internet connection is required. GitHub's code preview does not run the game; use **Download raw file** on the file page, then open the downloaded file. The repository is not automatically hosted as a live website.

The field manual appears on launch. The simulation starts paused. Click **Resume** or press **Space** to advance one day per real second; 2× and 4× speeds are available. Time stops when the tab is hidden or a campaign dialog is open.

### Army command

- Click a division counter on the map or a division in the Army panel.
- Right-click an adjacent province to move or attack. Alternatively, click **Move / attack**, then click or tap the destination.
- Infantry needs two days to move; armor needs one; mountains require four. Battles must resolve before movement into defended provinces.
- Green bars show organization. Gold bars show strength. Low organization forces retreat; encircled divisions may be destroyed.
- **Assign army** assigns all current divisions to the Eastern Army plan. **Execute plan** directs assigned divisions along friendly territory toward the nearest hostile frontier. **Halt plan** pauses that plan, while **Hold all** stops all orders and clears assignments. New recruits must be assigned separately with **Assign army**.
- Army plans are deliberately simple: there is no user-drawn front line or offensive line yet. Orange borders show the active front automatically.
- Drag the map to pan, scroll or use +/− to zoom, and switch political/supply/terrain overlays. Enter selects focused map elements; Escape cancels destination selection.

### Industry and mobilization

Allocate military factories between rifles and tanks. Territory losses reduce active factory count. Use civilian construction to add military factories (28 days) or forts (10 days). One construction project runs at a time; losing its province cancels it.

Train infantry for 5,000 manpower and 300 rifles (10 days), or armor for 2,400 manpower, 150 rifles, and 40 tanks (16 days). Up to four divisions train simultaneously and deploy at Asterhaven. Reserve equipment is consumed at the start.

Fuel regenerates each day. Active armored divisions consume five fuel daily. Resting, supplied divisions reinforce using rifles and manpower. Enemy reinforcement is simplified and does not simulate an equipment economy.

### Supply, research, politics, and diplomacy

- Supply flows through connected friendly territory from each nation's capital. Distance reduces supply beyond six provinces. Disconnected divisions suffer attrition and low organization.
- Weapons research improves combat power; industrial research improves equipment output. Each takes 24 days and has three levels.
- National focuses grant manpower, factories, better supply reach, political stability, or armor bonuses. Prerequisites unlock branches.
- Political power funds conscription, improved relations, fuel agreements, alliances, and ceasefires. Stability affects manpower recovery. War support is presently an informational statistic.
- Allies remain nonbelligerent in this prototype. Fuel agreements add eight fuel daily. Diplomatic relationships do not grant military access. Ceasefires preserve current borders.

### Campaign objective

Capture **Karsk City** and more than half of Karsk's original provinces. Karsk then capitulates and the campaign ends in victory. Losing **Asterhaven** ends in defeat. There is no post-victory continuation in this version.

### Saves

Use **Campaign → Save campaign / Load campaign**. Saves stay in this browser on this device and are separate from the earlier prototype's saves. Clearing browser data removes them. File-based local-storage behavior can vary by browser; if storage is blocked, the game displays an error. Loading always pauses time. Saves restore canonical province geometry and names rather than trusting those fields in stored data.

## Development

No runtime or build dependencies. Node.js 18+ is enough:

```sh
npm run build
npm test
```

- `src/engine.js`: deterministic campaign rules; importable in Node for testing.
- `src/ui.js`: map rendering and browser controls.
- `src/style.css`: responsive command interface.
- `src/shell.html`: accessible page structure and dialogs.
- `build.cjs`: bundles the source into standalone `index.html`.
- `tests/engine.test.cjs`: meaningful rules and state validation tests.

Rebuild `index.html` after source changes. The generated file is checked in so players can download it directly.

## Scope

75 provinces, six fictional nations, one playable country, infantry and armor, sustained land combat, automatic front lines, a simple army plan, factories, supply, research, focus branches, diplomacy, and local saves. Geography and campaign events are fictional. The presentation and mechanics take inspiration from WWII grand strategy, but this is not a clone or full-scale replacement for Hearts of Iron IV.

Not implemented: air/naval warfare, custom division templates, drawn battle plans, multiplayer, fog of war, rail-network logistics, naval invasions, generals with skill trees, advanced political simulation, or cloud saves. The whole map is visible. The AI receives periodic reinforcements during war and uses the same movement/combat rules, but does not manage a player-like economy.
