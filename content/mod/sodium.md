{
  "title": "Sodium",
  "description": "A Minecraft mod designed to improve frame rates and reduce micro-stutter",
  "icon": "https://media.forgecdn.net/avatars/thumbnails/284/773/64/64/637298471098686391.png",
  "homepage": "https://www.curseforge.com/minecraft/mc-mods/sodium",
  "issues": "https://github.com/jellysquid3/sodium-fabric/issues",
  "source": "https://github.com/jellysquid3/sodium-fabric",
  "releases": "https://www.curseforge.com/minecraft/mc-mods/sodium/files",
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
    "lithium",
    "phosphor"
  ],
  "dependency_type": [
    "Recommended",
    "Recommended"
  ]

}

Sodium is made possible thanks to my supporters on Patreon, who help fund the time that goes into developing these mods. You won't receive any special perks other than a badge of recognition, but you will get the nice feeling of supporting your favorite projects. You can click [here](https://patreon.com/jellysquid) or the button below to make a pledge to my page. Additionally, we have an official Discord server for all things related to my mods.

[![](https://i.imgur.com/ETo6sV0.png)](https://patreon.com/jellysquid) [![](https://i.imgur.com/S2a8uqH.png)](https://jellysquid.me/discord)

![](https://i.imgur.com/KarVVbr.png)

_Frame rate comparison between vanilla Minecraft and Sodium at a render distance of 32 chunks. You can find a world download with this exact scene here for your own comparison against this reference. Mileage may vary depending on how powerful your hardware is._

### Sodium

![](https://img.shields.io/github/license/jellysquid3/sodium-fabric?style=flat-square)

Sodium is a free and open-source rendering engine replacement for the Minecraft client that greatly improves frame rates, reduces micro-stutter, and fixes graphical issues in Minecraft. It boasts wide compatibility with the Fabric mod ecosystem when compared to other mods and doesn't compromise on how the game looks, giving you that authentic block game feel.

If you're coming from Optifine, you can generally expect a significant improvement to performance over it, but you'll be missing some small features while the Fabric community builds other free and open-source alternatives. For a quick list of replacement features (such as zoom), take a look [here](https://gist.github.com/modmuss50/deff1658c4550ca8b16cb5d40ceaa468). Sodium and Optifine are incompatible with one another. You must pick one.

You can find more comparisons for various hardware configurations, such as...

- [Intel i5-7200U @ 2.5GHz / Intel HD 620 (37->69fps)](https://imgur.com/0JrlAuf)
- [Intel i7-3770 @ 4.0GHz / GTX 960 (user-submitted) (27->152fps)](https://imgur.com/gthEOTt)
- [Intel i3-6100 / GTX 750 Ti (user-submitted) (10->102fps)](https://imgur.com/tGuLKNN)
- [Intel i7-8700K @ 5.0GHz / RTX 2080 Ti (user-submitted) (87->368fps)](https://imgur.com/Q9z0vbB)
- [AMD Ryzen 5 2600 / RX 580 (user-submitted) (133->586fps)](https://imgur.com/6WHjQR9)

You can even find some exotic and low-end systems running Sodium:

- [Raspberry Pi 4B / 4GB Variant (user-submitted) (17->36fps)](https://imgur.com/RIGL7xp)
- [AMD Athlon X2 QL-45 / ATI Radeon 4530 (user-submitted) (18->49fps)](https://imgur.com/7skXO7M)

**Note:** Sodium is mostly stable at this point, but it does not yet contain support for the Fabric Rendering API, which a small number of mods currently use. If you try to use these mods with Sodium, your game may crash or behave unexpectedly.

### Features

- A modern OpenGL rendering pipeline for chunk rendering that takes advantage of multi-draw techniques, allowing for a significant reduction in CPU overhead (~90%) when rendering the world. This can make a huge difference to frame rates for most computers that are not bottle-necked by the GPU or other components. Even if your GPU can't keep up, you'll experience much more stable frame times thanks to the CPU being able to work on other rendering tasks while it waits.
- Vertex data for rendered chunks is made much more compact, allowing for video memory and bandwidth requirements to be cut by almost 40%.
- Nearby block updates now take advantage of multi-threading, greatly reducing lag spikes caused by chunks needing to be updated. ([before](https://streamable.com/lm5sp5), [after](https://streamable.com/nsdl0r))
- Chunk faces which are not visible (or facing away from the camera) are culled very early in the rendering process, eliminating a ton of geometry that would have to be processed on the GPU only to be immediately discarded. For integrated GPUs, this can greatly reduce memory bandwidth requirements and provide a modest speedup even when GPU-bound.
- Plentiful optimizations for chunk loading and block rendering, making chunk loading significantly faster and less damaging to frame rates. ([before](https://streamable.com/3taw22), [after](https://streamable.com/4pesh2))
- Many optimizations for vertex building and matrix transformations, speeding up block entity, mob, and item rendering significantly for when you get carried away placing too many chests in one room.
- Many improvements to how the game manages memory and allocates objects, which in turn reduces memory consumption and lag spikes caused by garbage collector activity.
- Many graphical fixes for smooth lighting effects, making the game run better while still applying a healthy amount of optimization. For example, take this [before and after](https://imgur.com/lYmlmgq) of a white concrete room in vanilla, or this [comparison while underwater.](https://imgur.com/QQMuOTy)
- Smooth lighting for fluids and other special blocks. ([comparison](https://imgur.com/z9HBcvq))
- Smooth biome blending for blocks and fluids, providing greatly improved graphical quality that is significantly less computationally intensive. ([comparison](https://imgur.com/Fud5oyF))
- Animated textures which are not visible in the world are not updated, speeding up texture updating on most hardware (especially AMD cards.)

...and much more, this list is still being written after the initial release.

### Installation

Make sure you have the latest version of [Fabric Loader](https://fabricmc.net/use/) installed. Afterwards, all you need to do is simply drop the mod into your mods folder. No other mods (not even the Fabric API!) are required in order to use Sodium. You do not need to create new worlds in order to take advantage of the mod.

### Configuration

Sodium replaces the video settings screen with a new and improved user interface that contains all the bells and whistles for configuring Sodium. Out of the box, Sodium will enable all optimizations which are supported on your system.

### Modpack Permissions

This is a **free and open-source project** on CurseForge, and as such-- of course you can include it in your modpack! While not required, it's much appreciated if you link back to Sodium's project page in your mods list or credits page.

### Reporting Issues

Please use the issue tracker linked at the top of the page to report bugs, crashes, and other issues. The Curseforge comments section is not the place to report these kinds of problems and will likely result in you being asked to forward it along.

### Common questions

These questions are asked extremely frequently. Please check that what you're asking isn't covered by this section before posting a comment. Otherwise, your comment will be deleted in order to remove clutter.

**Will you port to Minecraft 1.15 and older? What about Minecraft 1.8.9?** No. Sodium is a modern mod designed for modern versions of Minecraft. Please stop asking.

**Will you add Forge support?** No. Forge compatibility is not being considered. You can read my thoughts [here](https://gist.github.com/jellysquid3/629eb84a74ab326046faf971150dc6c3) on why that decision was made.

**Does Sodium support Optifine shader packs?** No. However, experimentation is being done and it is possible in the future that Sodium could provide its own shader pack system. No promises are being made.

**Is Sodium a replacement for Optifine?** If you need the best performance out of your game, it very well could be. The primary focus of Sodium is optimization and improving rendering quality right now, not features. If you're looking for all the other features of which Optifine provides, check out this list for some Fabric-based alternatives (such as zoom functionality) which are compatible with Sodium.

[![](https://i.imgur.com/ztFQmY0.png)](https://upcloud.com/signup/?promo=6QG42H)

UpCloud (a high-performance cloud server provider) is currently offering a free trial that comes with **$25 USD in account credit** to any new users who sign up using my referral code. In the free trial, you can spin up a server instance with **1 CPU/1 GB RAM/25 GB SSD/1TB Transfer** for $5/mo using your credits without making a payment.

Their servers are very speedy and use the latest AMD EPYC 7542 processors (see my [Geekbench score](https://browser.geekbench.com/v5/cpu/3057414)) with excellent CPU throughput, performance stability, and I/O performance. If you're familiar with managing your own cloud servers and don't want the fluff that comes with managed Minecraft hosting, they might be a good choice.

They are not sponsoring me, and as such they definitely cannot stop me from saying bad things about their products. But, if you make a deposit to upgrade your account, they will provide me with a small kickback. A win-win for everyone. You can click [here](https://upcloud.com/signup/?promo=6QG42H) to sign up using my promo code.
