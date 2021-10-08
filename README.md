# rlImGui
<img align="left" src="https://github.com/raysan5/raylib/raw/master/logo/raylib_logo_animation.gif" width="64">
A Raylib integration with DearImGui

rlImgui provides a backend for [Dear ImGui](https://github.com/ocornut/imgui) using [Raylib](https://www.raylib.com/). 

# Setup

Using rlImGui in your code is very easy. Once you have included the library, or source files for rlImGui and ImGui in your project, simply do the following.
```
#include "rlImGui.h"	// include the API header

// before your game loop
rlImGuiSetup(true); 	// sets up ImGui with ether a dark or light default theme

// inside your game loop, between BeginDrawing() and EndDrawing()
rlImGuiBegin();			// starts the ImGui content mode. Make all ImGui calls after this

rlImGuiEnd();			// ends the ImGui content mode. Make all ImGui calls before this

// after your game loop is over, before you close the window

rlImGuiShutdown();		// cleans up ImGui
```

# Examples
There are two example programs in the examples folder.

## Simple
This is the most simple use of ImGui in raylib, it just shows the ImGui demo window.

## Editor
This is a more complex example of ImGui, showing how to use raylib 2d and 3d cameras to draw into ImGui windows using render textures.

# Extras

## rlImGuiColors.h
This file has a converter to change Raylib colors into ImGui Colors

## Icon Fonts
The extras folder has files to help add icon fonts into ImGui. Functions to load the font and #defines for the font glyps are included in each header.

### Font Awesome
This is a header in the extras folder to add icons from Font Awesome into ImGui.
https://fontawesome.com/
Simply call the add function to include the fonts in ImGui
```
rlImGuiAddFontAwesomeIconFonts(12); 
```

### ForkAwesome
This is a header in the extras folder to add icons from Fork Awesome into ImGui.
https://forkaweso.me/Fork-Awesome/
Simply call the add function to include the fonts in ImGui
```
rlImGuiAddForkAwesomeIconFonts(12); 
```

# Images
Raylib textures can be drawn in ImGui using the following functions
```
void rlImGuiImage(const Texture *image);
void rlImGuiImageSize(const Texture *image, int width, int height);
void rlImGuiImageRect(const Texture* image, int destWidth, int destHeight, Rectangle sourceRect);
```

# C vs C++
ImGui is a C++ library, so rlImGui uses C++ to create the backend and integration with Raylib.
The rlImGui.h API only uses features that are common to C and C++, so rlImGui can be built as a static library and used by pure C code. Users of ImGui who wish to use pure C must use an ImGui wrapper, such as [https://github.com/cimgui/cimgui].

