# Solar Expanse Expanded

> Rebalances the fuel-power branch and gives a dozen dead-end research nodes a reason to exist — new facility tiers, real payoffs for "finished" tech, and a fixed early-game power plant.

<!-- SCREENSHOT: hero shot — the expanded research tree with newly-reachable nodes highlighted. File: docs/images/solarexpanseexpanded-hero.png -->

## What it does

- **Fixes the chemical power plant's free-power bug
  ** and retunes it as a real early-game fuel-burning baseline, comparable in cost and output to solar/wind rather than a throwaway option.
- **Every fuel-burning power plant load-follows.
  ** Chemical, carbon, fusion, hydrogen, and nuclear plants can now throttle output to match demand instead of running flat-out or fully off.
- **Unlocks a big-tier fuel power plant** (
  `build_power_fuel_big`) — chemical's industrial ×10 sibling — by finally connecting the orphaned Chemical Power Reactor research node to the rest of the tree, so it's reachable from a normal playthrough for the first time.
- **Rebalances big-tier glass and electrolysis plants
  ** to a consistent cost/time scaling rule instead of a leftover ×1000 placeholder, and gates them behind research so they're earned, not free.
- **Gives payoff to research "dead ends."
  ** Six previously pointless leaf nodes — Solid Propellant Rockets, Microprocessors, Early Launch Systems, Exoplanet Detection, Expanded Cargo Bays 4, and Advanced Payload Fairings — now grant real bonuses (launch-vehicle build speed, research production, launch cost, observation speed, maintenance reduction) instead of ending the branch with nothing.
- **Unlocks the asteroid engine facility and its contract
  ** through the Mass Driver Propulsion research line, plus a gas-mining efficiency boost and an electrolysis yield bonus tied to their respective research nodes.

## Before / after

Vanilla: the chemical power plant silently produces power for free (missing fuel input), several big-tier facilities are stranded behind orphaned research nodes nothing points to, and a handful of finished research branches grant nothing. This pack fixes the bug, reconnects the tree, and pays off the dead ends.

## Requirements

- Solar Expanse + BepInEx 5 (Mono/x64), **plus the third-party Teddit data-mod loader
  ** — this pack is Teddit YAML content, not a standalone code mod, and does nothing without it installed.

## Install

1. Install BepInEx 5, then install Teddit (its own plugin) into `BepInEx/plugins/`.
2. Drop this pack's `ResearchTreeExpansion` folder into `BepInEx/plugins/Teddit/mods/`.
3. Launch the game — Teddit loads `facilities.yaml` and
   `research.yaml` and patches the base research tree/facilities in place.

## Building (developers)

`dotnet build` runs the `DeployTedditMod` MSBuild target, which copies
`TedditMod/ResearchTreeExpansion/*.yaml` straight into
`$(GameDir)/BepInEx/plugins/Teddit/mods/ResearchTreeExpansion/`. The project also builds a BepInEx plugin DLL shell (
`SolarExpanseExpanded.dll`), but it currently has no Harmony patches and isn't deployed to
`BepInEx/plugins/` — all real content ships as YAML.
