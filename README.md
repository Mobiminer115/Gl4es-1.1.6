# GL4ES 1.1.6 — Amethyst iOS renderer workbench

Dedicated workbench for the GL4ES 1.1.6 renderer used by the `Mobiminer115/Amethyst-iOS` fork.

## Baseline

- Upstream: `ptitSeb/gl4es`
- Target baseline: `v1.1.6`
- Target platform: iOS / arm64
- Primary target: Java 8 / Minecraft 1.16.x and older

## Integration strategy

The Amethyst fork keeps the existing `libgl4es_114.dylib` loader filename initially. CI builds upstream GL4ES `v1.1.6` for iOS and stages that binary at the existing path, giving us a low-risk drop-in baseline before changing renderer selection or launcher logic.

This repository is kept separate so iOS-specific build fixes, compatibility patches, performance experiments, and benchmark notes can be developed without mixing them into the launcher code.

## Optimization policy

No blind performance hacks. Changes should be validated against:

- Minecraft 1.7.10
- Minecraft 1.8.9
- Minecraft 1.12.2
- Minecraft 1.16.5
- Forge/Fabric modpacks where applicable
- OptiFine and shader compatibility where applicable
- frame-time stability, not only average FPS

The first milestone is a clean GL4ES 1.1.6 iOS build and a working drop-in replacement for the current GL4ES binary. Only after that should renderer internals be optimized.

## License

GL4ES is distributed under the MIT license. See the upstream project for the canonical license and source history.
