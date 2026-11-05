# Enchanted Forest Endless Runner

A 3D, lane-based endless runner built natively in **Unity** with the **Universal
Render Pipeline**. The player pilots a forest spirit along a winding, moonlit
trail — dodging fallen enchanted roots, catching glowing spirit fireflies, and
surviving as far as possible while the run grows faster.

The project is completely **asset-free**: every material, light, particle
effect, post-processing volume, and sound is generated procedurally at runtime
from C#. One component — `Bootstrap` — builds the entire world and drives the
full run loop.

## Tech stack

| Item | Value |
|---|---|
| Unity | 6000.3.22f1 |
| Render pipeline | URP (`com.unity.render-pipelines.universal` 17.3.0) |
| Input | New Input System (`com.unity.inputsystem` 1.20.0) |
| UI | uGUI Canvas built in code |
| Namespace | `EnchantedForest` |

## Getting started

1. Open the project in **Unity 6000.3.22f1** (the `ProjectSettings` folder).
2. Make sure **Assets/Scenes/SampleScene** is open.
3. Right-click in the Hierarchy → **Create Empty**, add the
   `EnchantedForest.Bootstrap` component. That's the whole scene.
4. Press **Play**. You'll see the title card; press **Space** (or click) to
   start.

See **[SETUP.md](SETUP.md)** for the full, step-by-step setup and troubleshooting.

## Controls

| Input | Action |
|---|---|
| `←` / `→` or `A` / `D` | Change lane |
| `Space` / `↑` | Jump |
| `R` (on the game-over screen) | Restart |

## Project structure

| File | Responsibility |
|---|---|
| `Assets/Scripts/Bootstrap.cs` | Builds the whole world + drives the streaming run loop |
| `Assets/Scripts/GameManager.cs` | Score, lives, distance, run state, combo, invulnerability (event-based singleton) |
| `Assets/Scripts/RunnerController.cs` | Lane / jump / forward movement, collisions, hit-blink |
| `Assets/Scripts/CameraRig.cs` | Smooth follow, look-ahead, impact shake |
| `Assets/Scripts/Entities.cs` | `Obstacle` marker + `FireflyPickup` trigger / spin / bob |
| `Assets/Scripts/GameHUD.cs` | Canvas HUD: distance, hearts, title card, game-over card + retry |
| `Assets/Scripts/ProceduralAudio.cs` | Runtime-synthesised hum, collect, and hit sounds (no audio files) |
| `Assets/Scripts/WorldFX.cs` | Particle bursts (collect / impact) + drifting ambient spores |
| `Assets/Scripts/WorldFactory.cs` | All materials, primitive shapes, and the URP post-processing volume |

## Development team

- Sunkari Sai — Roll No. 2303A52492
- Bolagani Sushanth — Roll No. 2403A52L11
- Ch. Charan Kumar — Roll No. 2303A54006

Project Guide & Mentor: Dr. Vijay Chandra Jadala
Academic Year 2026 – 2027
