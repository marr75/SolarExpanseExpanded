# SolarExpanseExpanded

A BepInEx 5 plugin for [Solar Expanse](https://store.steampowered.com/) that expands the
research tree via [Teddit](https://github.com/) YAML data — adding gating for gas mining,
power/chemical facilities, and related unlocks on top of the base game's tree. The plugin
itself (`Plugin.cs`) is currently a scaffold with no Harmony patches; the mod's content today
is the Teddit data-mod deployed under `TedditMod/ResearchTreeExpansion/`.

Requires the [Teddit](https://github.com/) mod loader to be installed, since the research-tree
YAML is consumed by Teddit rather than by this plugin directly.

## Build

Set the `SOLAR_EXPANSE_DIR` environment variable to your Solar Expanse install directory, then:

```powershell
$env:SOLAR_EXPANSE_DIR = 'C:\Path\To\Solar Expanse'
dotnet build
```

Building deploys the research-tree YAML to `$(GameDir)\BepInEx\plugins\Teddit\mods\ResearchTreeExpansion\`.

## License

MIT (see LICENSE)
