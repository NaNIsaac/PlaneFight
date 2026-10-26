# PlaneFight

A small vertical-scrolling shooter written in C++ with raylib.

Hobby project from 2023. Enemy planes and bombers fly down from the top of the screen; the
player plane moves along the bottom and shoots them; the kill count and elapsed time are shown top-left. The game ends when an enemy reaches the player.

## Screenshots

![Title menu](docs/media/screenshot-1.png) ![During play](docs/media/screenshot-2.png)

![Short gameplay recording](docs/media/demo.gif)

## Requirements

- Windows, Visual Studio 2022 with "Desktop development with C++" (toolset v143)
- raylib 4.2 and a small logging library, bundled as 32-bit headers and libraries in
  `include/` and `lib/`

## Run

1. Open `PlaneFight.sln`.
2. Run (F5). The build copies `lib\raylib.dll` next to the exe. Sprites and sounds are loaded from `asset/`, so the working directory must be the
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

Built with MSBuild from the Visual Studio 2022 Build Tools (MSVC 14.44, Win32); only C4244/C4018 conversion
warnings are reported:

```
MSBuild PlaneFight.sln -p:Configuration=Debug
Debug\PlaneFight.exe
```

Start the executable from the repository root so that `asset/` is found. The window is 960x540.

## Author

Written alone by [NaNIsaac](https://github.com/NaNIsaac) in 2023.

## License and third-party material

The game source (`*.cpp`, `*.h` in the repository root, and the project files) is under the
[MIT License](LICENSE).

- **raylib 4.2** - zlib/libpng license, Copyright (c) 2013-2022 Ramon Santamaria. The headers `include/raylib.h`,
  `raymath.h` and `rlgl.h` carry its notice unchanged. `lib/raylib.dll`, `raylib.lib` and `raylibdll.lib` are
  raylib builds.
- **Logging** - `include/logger.h` and `lib/logger.lib` are a small logging class used by the game. Their origin
  is not recorded in this repository.
- **`asset/`** - five PNG sprites and one WAV sound. Their origin and license are not recorded in this
  repository (the metadata of `enemy2.png` names Inkscape as the tool). Until that is documented here, the MIT
  License does not extend to the files in `asset/`.
