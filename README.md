# Dalamud  [![Actions Status](https://github.com/ottercorp/Dalamud/workflows/Build%20Dalamud/badge.svg)](https://github.com/ottercorp/Dalamud/actions) [![Discord Shield](https://discordapp.com/api/guilds/581875019861328007/widget.png?style=shield)](https://discord.gg/3NMcUV5)

<p align="center">
  <img src="https://raw.githubusercontent.com/ottercorp/DalamudAssets/master/UIRes/logo.png" alt="Dalamud" width="200"/>
</p>

Dalamud is a plugin development framework for FINAL FANTASY XIV that provides access to game data and native interoperability with the game itself to add functionality and quality-of-life.

It is meant to be used in conjunction with [FFXIVQuickLauncher](https://github.com/ottercorp/FFXIVQuickLauncher), which manages and launches Dalamud for you. __It is generally not recommended for users to try to run Dalamud manually as there are multiple dependencies and assumed folder paths.__

## Hold Up!
If you are just trying to **use** Dalamud, you don't need to do anything on this page - please [download XIVLauncher](https://ottercorp.github.io/) from its official page and follow the setup instructions.

## Plugin development
Dalamud features a growing API for in-game plugin development with game data and chat access and overlays.
Please see our [Developer FAQ](https://ottercorp.github.io/faq/development) and the [API documentation](https://ottercorp.github.io/Dalamud/api/index.html) for more details.

If you need any support regarding the API or usage of Dalamud, please [join our discord server](https://discord.gg/3NMcUV5).

<br>

Thanks to Mino, whose work has made this possible!

## Components & Pipeline

These components are used in order to load Dalamud into a target process.
Dalamud can be loaded via DLL injection, or by rewriting a process' entrypoint.

| Name | Purpose |
|---|---|
| *Dalamud.Injector.Boot* (C++) | Loads the .NET Core runtime into a process via hostfxr and kicks off Dalamud.Injector |
| *Dalamud.Injector* (C#) | Performs DLL injection on the target process |
| *Dalamud.Boot* (C++) | Loads the .NET Core runtime into the active process and kicks off Dalamud, or rewrites a target process' entrypoint to do so |
| *Dalamud* (C#) | Core API, game bindings, plugin framework |
| *Dalamud.CorePlugin* (C#) | Testbed plugin that can access Dalamud internals, to prototype new Dalamud features |

## Branches

We are currently working from the following branches.

| Name | Purpose | .NET Version | Track |
|---|---|---|---|
| *master* | Current release branch | .NET 6.0.3 (March 2022) | Release & Staging |
| *net7* | Upgrade to .NET 7 | .NET 7.0.0 (November 2022) | net7 |
| *api3* | Legacy version, no longer in active use | .NET Framework 4.7.2 (April 2017) | - |

<br>

##### Final Fantasy XIV © 2010-2021 SQUARE ENIX CO., LTD. All Rights Reserved. We are not affiliated with SQUARE ENIX CO., LTD. in any way.
