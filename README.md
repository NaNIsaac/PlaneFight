# PlaneFight

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
