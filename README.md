# PlaneFight

Moved to games-2023/PlaneFight (https://github.com/NaNIsaac/games-2023/tree/main/PlaneFight). This repo is no longer maintained.

A small vertical-scrolling shooter written in C++ with raylib.

Hobby project from 2023. Enemy planes and bombers fly down from the top of the screen; the
player plane moves along the bottom and shoots them; the kill count and elapsed time are shown top-left. The game ends when an enemy reaches the player.

## Requirements

- Windows, Visual Studio 2019 or later with "Desktop development with C++" (toolset v142;
  newer Visual Studio versions offer to retarget)
- raylib 4.2 and a small logging library, bundled as 32-bit headers and libraries in
  `include/` and `lib/`

## Run

1. Open `PlaneFight.sln`.
2. Select the `Debug` / `x86` configuration and build.
3. Copy `lib\raylib.dll` next to the built `PlaneFight.exe` (in `Debug\`).
4. Run (F5). Sprites and sounds are loaded from `asset/`, so the working directory must be the
   repository root (the Visual Studio default).

## Controls

- Left / Right arrow: move
- Space: shoot
- On-screen `Pause` and `Quit` buttons (mouse)
- Space or any letter/number key: start from the menu, resume from pause, return to the menu after game over
- Esc: close the window

## Structure

- `main.cpp` - window setup and main loop
- `game.cpp` - player, bullets, enemies, collisions
- `sprite.cpp`, `screen.cpp`, `loading.cpp` - sprites, UI, resource loading

## Build from the command line

Rebuilt on 2026-10-23 without source changes, using MSBuild from the Visual Studio 2022 Build Tools
(MSVC 14.44) with the toolset overridden to v143; only C4244/C4018 conversion warnings were reported:

```
MSBuild PlaneFight.sln -p:Configuration=Debug -p:Platform=x86 -p:PlatformToolset=v143
copy lib\raylib.dll Debug\
Debug\PlaneFight.exe
```

Start the executable from the repository root so that `asset/` is found. The window is 960x540.

## Origin

This repository's history was imported into [games-2023](https://github.com/NaNIsaac/games-2023) as
`PlaneFight/` with `git subtree` (games-2023 commit `b2340dc`, from commit `cd604ce` here). Apart from
line endings, the files there are identical to this repository's.
