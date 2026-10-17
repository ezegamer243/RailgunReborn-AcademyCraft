# RailgunReborn – AcademyCraft

An **unofficial port and rewrite** of [AcademyCraft](https://github.com/LambdaInnovation/AcademyCraft) for **Minecraft 1.21.1** on **NeoForge**.

Awaken a supernatural ability, train it and push it to its limits. Inspired by *A Certain Magical Index / A Certain Scientific Railgun*, AcademyCraft turns you into an esper with one of four ability categories, each with its own skill tree, levels and progression.

> All credit for the original design, art and sounds goes to **LambdaInnovation**, the creators of AcademyCraft. This project is a fan-made port rebuilt from scratch for modern Minecraft; it is not affiliated with or endorsed by LambdaInnovation.

## Features

### Ability categories
- **Electromaster**: Arc Generation, Current Charging, Magnet Movement, Body Intensify, Thunder Bolt, Thunderclap, Mine Detection, Magnet Manipulation and the **Railgun**.
- **Meltdowner**: Electron Bomb, Scatter Bomb, Light Shield, Rad Intensify, Mine Ray, Ray Barrage, Jet Engine, Electron Missile and the **Meltdowner** beam.
- **Teleporter**: Threatening Teleport, Flesh Ripping, Location / Mark / Shift / Penetrate Teleport, Flashing, Space Fluctuation and Dimension Folding Theorem.
- **Vector Manipulation**: Directed Shock, Ground Shock, Vector Acceleration, Vector Deviation, Directed Blastwave, Storm Wing, Blood Retrograde, Vector Reflection and **Plasma Cannon**.

Every category has 5 levels, CP and overload management, skill experience, key-bound presets and an in-game skill tree.

### Survival progression
- New ores (Constraint Metal, Imag Crystal, Imag Silicon, Resonant Crystal) and underground lakes of **Imag Phase Liquid**.
- Machines: **Imag Fusor** and **Metal Former**.
- **Ability Developers** (portable, normal, advanced) to awaken a category, level up and learn skills.
- **Ability Induction Factors**: rare structure-chest loot (any mod's chests) used to choose a category.
- **Category Reactor**: a new 3×3×3 late-game multiblock that switches your ability category.
- **Data Terminal**, installed with a craftable Terminal Installer.

### Energy
- Forge Energy (FE) internally, displayed as "IF", so it interoperates with other tech mods.
- Solar, Phase and multiblock Wind generators; Energy Unit, High Battery and Mega Battery.
- **Wireless energy network**: Wireless Matrix + three tiers of Wireless Nodes, configured in-game with a network name and password.
- Server config (`serverconfig/railgunreborn-server.toml`): `energyRequired`, `reactorChargeRate`, `generatorMultiplier`.

### Compatibility
- **JEI** (optional): machine recipe categories, energy costs and info pages.
- Singleplayer and multiplayer (install on both server and client).

## Privacy

The original mod sent analytics to a remote server, looked up the player's public IP and downloaded a donor list. **All of that was removed.** This port makes **no internet connections**; the "wireless" network exists only inside the game. The build enforces this: the `checkPrivacy` Gradle task fails if networking code appears in the sources. See [`PRIVACY.md`](PRIVACY.md).

## Installing

1. Install **Minecraft 1.21.1** with **NeoForge 21.1.176** or newer.
2. Drop `railgunreborn-<version>.jar` into your `mods/` folder (server **and** every client).
3. Optional: add JEI for 1.21.1 (NeoForge).

## Building from source

Requirements: **JDK 21**. Gradle is provided by the wrapper.

```bash
./gradlew build
```

The jar is written to `build/libs/`. On Windows use `gradlew.bat`.

Other useful tasks:

| Task | What it does |
|---|---|
| `./gradlew runClient` | Starts a development client (JEI included in dev). |
| `./gradlew runServer` | Starts a development server. |
| `./gradlew runGameTestServer` | Runs the in-game GameTests (server-side behaviour) and exits. |
| `./gradlew test` | Runs the JUnit unit tests (pure rules, layouts, resources, event-bus checks). |
| `./gradlew checkPrivacy` | Fails if any networking code is found (also runs with `check`/`build`). |

### Project layout

```
src/main/java/com/railgunreborn/
  ability/      ability system, categories and every skill
  block/        machines, generators, developers
  client/       rendering, HUD, screens, effects
  compat/jei/   optional JEI plugin
  energy/       FE helpers (storages, battery slots, pushing)
  wireless/     wireless matrix, nodes and network data
  reactor/      Category Reactor multiblock
  metalformer/  Metal Former
  gametest/     GameTests
src/test/java/  JUnit tests
src/main/resources/assets/railgunreborn/  models, textures, sounds, lang (en_us, es_es)
```

## License

- **GPL-3.0**, the same license as the original AcademyCraft. See [`LICENSE`](LICENSE).
- By the original authors' terms, **selling this mod or its contents in any form is prohibited**, including selling abilities, items or ranks that grant abilities on servers.
- Modpacks are allowed.
- Original art, models and sounds belong to LambdaInnovation and are reused under the original license; see [`CREDITS.md`](CREDITS.md).

## Credits

- **AcademyCraft** and **LambdaLib2** by **LambdaInnovation**: <https://github.com/LambdaInnovation/AcademyCraft>
- **Port** by **Zeryu**
- Built on the official NeoForge MDK (ModDevGradle).
