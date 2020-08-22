{
  "title": "Lithium",
  "description": "An optimization mod for Minecraft which improves server performance significantly",
  "icon": "https://media.forgecdn.net/avatars/thumbnails/246/646/64/64/637158441743060329.png",
  "homepage": "https://www.curseforge.com/minecraft/mc-mods/lithium",
  "issues": "https://github.com/jellysquid3/lithium-fabric/issues",
  "source": "https://github.com/jellysquid3/lithium-fabric",
  "wiki": "https://github.com/jellysquid3/lithium-fabric/wiki/",
  "releases": "https://www.curseforge.com/minecraft/mc-mods/lithium/files",
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
    "phosphor"
  ],
  "dependency_type": [
    "Recommended",
    "Recommended"
  ]

}

Want to help support development?

Lithium is made possible thanks to the awesome supporters [on my Patreon](https://patreon.com/jellysquid). Each pledge allows me to spend more time working on mods like these while helping to cover a few expenses. You'll also gain some special perks on the [official Discord server](https://jellysquid.me/discord) and access to prioritized support.

[![](https://i.imgur.com/ETo6sV0.png)](https://patreon.com/jellysquid) [![](https://i.imgur.com/S2a8uqH.png)](https://jellysquid.me/discord)

![](https://i.imgur.com/aPu88TC.png)

_Server tick time (mspt) graph before and after installing Lithium. Measurements made in an existing world at a render distance of 18._

### Lithium

![](https://img.shields.io/github/license/jellysquid3/lithium-fabric?style=flat-square)

Lithium is a general-purpose optimization mod for Minecraft which works to improve a number of systems (game physics, mob AI, block ticking, etc) without changing any behavior. It works **on both the client and server**, and can be installed on servers **without requiring clients to also have the mod**. With the mod installed, you can see on average a **45% improvement to server tick times**, resulting in a much leaner game.

Even in single-player, your game runs an "integrated server" which ticks the world your player is in. Through optimizing the server-side of the game, this can free up your computer's processor to focus on other tasks, resulting in **improved frame rates and responsiveness**. For multiplayer servers, administrators can expect a sizeable improvement to tick times, allowing their hardware to support more loaded entities, chunks, and players.

If you aren't using it already as well, [Phosphor](https://fabric-selects.github.io/mod/phosphor/) and [Sodium](https://fabric-selects.github.io/mod/sodium/) both pair great with Lithium and are fully compatible.

### Installation

Make sure you have the latest version of Fabric Loader present and then simply drop the mod into your mods folder. No other mods or additional setup (not even Fabric API!) is required.

You do not need to create new worlds in order to take advantage of the mod.

### Features

You might be curious by now as to what exactly Lithium is doing in order to achieve such significant gains, and I'm happy you are! You can read about (some) of the changes we make below.

**Physics optimizations:** Entity collision detection has seen significant improvements through reducing the collision resolution complexity for simple, cuboid blocks. A more accurate algorithm is also used to reduce the number of blocks being checked every tick, especially in cases where entities are moving very quickly.

**Mob AI optimizations:** We make use of an event-based system for some tasks in order to reduce the CPU usage incurred by constantly polling the world for changes. Mob "brains" have also been optimized to select between different AI tasks much, much quicker than before. Comparison before and after [here](https://i.vgy.me/ViqOVw.png).

**World generation optimizations:** Many calculations in vanilla's world generation are unnecessary and do not affect the final result, which gives ample opportunity for Lithium to optimize this overhead away.

**Chunk loading optimizations:** The temporary data structures used in block palette compaction have been changed to be much more efficient. This results in fewer TPS drops while players are exploring terrain and provides a modest boost to world load times. We also batch some verification operations to reduce unnecessary disk I/O.

**Mob farm optimizations:** Mob cramming is [significantly less expensive](https://i.vgy.me/Dwd470.png) as resolving collisions between entities has been optimized to take advantage of the fact that simple boxes are involved. This makes mob farms considerably less harmful for server tick rates.

**Block ticking optimizations:** has less overhead, making things such as block update settling after generating chunks and other Redstone contraptions faster. This also reduces the amount of time it takes for a block to determine if it is ticking by schedule from O(n), where n is the number of ticking blocks, to O(1), providing a significant speedup when many blocks are being ticked.

**Explosion optimizations:** Many optimizations have been applied to TNT and explosions alike, reducing their associated lag without changing how they behave. In particular, ray-tracing is optimized to take advantage of the fact that multiple steps through a way will occur in the same block position, allowing us to quickly re-use the previous step's results. We also make use of a faster position tracking algorithm which avoids many excessive allocations.

**Point of Interest optimizations:** Complex mob AIs in Minecraft, primarily those belonging to Villagers and Pillagers, often need to find relevant points of interest in the world in order to choose the most appropriate AI task. In vanilla, querying all points within a chunk requires 16 separate retrievals through stream-heavy code. With Lithium present, this task is reduced to a single simple retrieval that makes use of a much faster (and traditional) iterator based approach, yielding anywhere from a 16-22x improvement for queries.

**Data Tracker optimizations:** The internal data manager used for tracking some entity state and properties has been optimized to use flat arrays and avoid expensive locking, providing a decent boost whenever these attributes are accessed during a game tick.

... And other internal improvements to help the JVM better optimize code.

### Configuration

Lithium makes use of an unusual configuration system which can be used to enable or disable certain patches. This system allows fine-grained control over what code is modified by Lithium, and as such, can be used to completely eliminate bugs or mod incompatibilities introduced by the mod. For more information, please read [the wiki entry](https://github.com/jellysquid3/lithium-fabric/wiki/Configuration-File) on modifying your configuration file. An empty configuration file is _perfectly normal_ and just means you want to use the default options.

### Modpack Permissions

This is a **free and open-source** project on CurseForge, and as such-- of course you can include it in your modpack! While not required, it's much appreciated if you link back to Lithium's project page and Patreon in your mods list or credits page.
Reporting Issues

Please use the issue tracker linked at the top of the page to report bugs, crashes, and other issues. The Curseforge comments section is not the place to report these kinds of problems and will likely result in you being asked to forward it along.
