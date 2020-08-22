{
  "title": "Phosphor",
  "description": "Performance improvements for Minecraft's lighting engine",
  "icon": "https://media.forgecdn.net/avatars/thumbnails/284/775/64/64/637298471783289760.png",
  "homepage": "https://www.curseforge.com/minecraft/mc-mods/phosphor",
  "issues": "https://github.com/jellysquid3/phosphor-fabric/issues",
  "source": "https://github.com/jellysquid3/phosphor-fabric",
  "releases": "https://www.curseforge.com/minecraft/mc-mods/phosphor/files",
  "discord": "https://jellysquid.me/discord",

  "categories": [
    "Optimization"
  ],

  "users": [
    "jellysquid"
  ],
  "user_type": [
    "Developer"
  ],
  "user_contribution_type": [
    "author"
  ],

  "dependencies": [
    "sodium",
    "lithium"
  ],
  "dependency_type": [
    "Recommended",
    "Recommended"
  ]

}

Want to help support development?

Phosphor is made possible thanks to the awesome supporters [on my Patreon](https://patreon.com/jellysquid). Each pledge allows me to spend more time working on mods like these while helping to cover a few expenses. You'll also gain some special perks on the [official Discord server](https://jellysquid.me/discord) and access to prioritized support.

[![](https://i.imgur.com/ETo6sV0.png)](https://patreon.com/jellysquid) [![](https://i.imgur.com/S2a8uqH.png)](https://jellysquid.me/discord)

![](https://i.imgur.com/CoQk2e7.png)

### Phosphor

![](https://img.shields.io/github/license/jellysquid3/phosphor-fabric?style=flat-square)

Phosphor is a Minecraft mod which works to optimize one of game's most inefficient areas-- the lighting engine. It works **on both the client and server**, and can be installed on servers **without requiring clients to also have the mod**. With Phosphor, the amount of time the game takes to generate chunks can be halved for some dimensions, and frame stuttering experienced while traversing the world can be significantly reduced. It's a no-compromises solution for improving performance either in single-player or large multi-player servers, and changes no features or behaviors of the vanilla game.

If you aren't using it already as well, my other optimization mods [Lithium](https://fabric-selects.github.io/mod/lithium/) and [Sodium](https://fabric-selects.github.io/mod/sodium/) both pair great with Phosphor and are fully compatible.

### Installation

Don't worry, it's fairly painless. Simply make sure you have the latest version of Fabric Loader present and then drop the mod into your mods folder. **The Fabric API is not required**. No other additional setup is required, and you do not need to create a new world in order to take advantage of the mod.

### What doesn't the mod do?

While this is a significant improvement of vanilla's lighting engine implementation, it does not make any changes to how the light model in Minecraft works. In layman's terms, this mod does not change how light is rendered (except where bugs are fixed) or add new features to Minecraft. This allows the mod to work without being installed on the opposite end client or server. The fixes and optimizations provided by Phosphor are specific to improving the lighting engine, keeping it small and self-contained. This mod doesn't cure all world generation lag or client-side hiccups, as lighting is only one part of the equation.

### Modpack Permissions

This is a free and open-source project on CurseForge, and as such-- of course you can include it in your modpack! While not required, it's much appreciated if you link back to Phosphor's project page and Patreon in your mods list or credits page.

### Reporting issues

Please use the issue tracker linked at the top of the page to report bugs, crashes, and other issues. The Curseforge comments section is not the place to report these kinds of problems and will likely result in you being asked to forward it to the issue tracker.
