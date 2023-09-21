# SDL_helloworld

## What is this?

This is a simple skeleton program that builds an extremely simple SDL-based
program, setting up CI for GitHub Actions and such.

Feel free to use this as a starting point for your own code.

This app just creates a window, fades it between shades of red, and draws a
white square wherever the mouse cursor travels in the window. It's just meant
to give you the idea of a basic SDL app.


## This is the SDL3 branch!

(FIXME: the SDL2 stuff hasn't been written yet.)
SDL3 is still a work in progress. If you want the SDL2 version, please use
the `SDL2` branch of this git repository instead.


## How to build for most platforms

For most platforms, you need build tools for whatever platform you are
targeting (Visual Studio, Xcode, Android NDK, Emscripten, etc), and a copy of
[CMake](https://cmake.org/) installed.

You'll also need a copy of SDL. You can build
[SDL from source code](https://github.com/libsdl-org/SDL), but you probably
just want to [download it](https://github.com/libsdl-org/SDL/releases/latest).

We can't document how to build for _every_ platform here, because it can be
a pretty complex topic, but here are some common ones.


## Build for Linux, Raspberry Pi, other Unix-like systems

Install SDL through your package manager or build from source code.

Get to a command line and run this from the source code's directory.

```bash
mkdir build
cmake ..
cmake --build .
```


## Build for Windows

Get SDL from the [download page](https://github.com/libsdl-org/SDL/releases/latest).

You'll want a download with "-devel" in the filename. The "VC" download is
for Visual Studio users, the "mingw" is for the MingW development tools.

There is a CMake GUI program you can use to avoid the command line here,
but here's the command line:

```bash
mkdir build
cmake ..
cmake --build .
```

(This will generally figure out your default compiler, but you might have to
give it a nudge if necessary.)


## How to build for Emscripten

(FIXME: this isn't correct yet)
Install the emsdk from [Emscripten's website](https://emscripten.org/), then:

```bash
source /where/i/installed/emsdk/emsdk_env.sh
mkdir build
emcmake cmake ..
cmake --build .
```

All the files that are named "index.*" can be put on a webserver. Web browsers
pointed at index.html will run the app.


## Build for other platforms

We are adding more platforms to this README as we can; please check back later
or [file a bug](https://github.com/libsdl-org/SDL_helloworld/issues/new) to
tell us about what you need!

Often, if you are familiar with a platform but CMake doesn't Just Work there,
you simply have to drop main.c into a new project, make sure it can find the
SDL libraries and headers, and build.

