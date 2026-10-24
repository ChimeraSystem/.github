# Chimera

An experimental x86_64 operating system with a Mach/BSD kernel, Mach-O userspace
and a native desktop.

Chimera boots through its own UEFI loader. Canvas handles windows, desktop
composition and HiDPI displays; applications use Foundation, AppKit and
ChimeraKit. GPU composition runs through Mesa and Virgl, with an ANGLE/Metal
path for development on macOS.

The system includes user accounts and a login screen, UFS2 storage, networking,
shared audio through audiod, and native applications such as Terminal, Files,
System Settings and Music. And Pacman, of course.

Native Clang/LLD, Ninja, CMake, Python and Meson are part of the work toward
self-hosting. QEMU is the current development target; bare-metal support and
building the whole OS inside Chimera are still in progress.

## Source

| Repository | Contents |
| --- | --- |
| [chimera](https://github.com/ChimeraSystem/chimera) | Build integration, packaging, tests and documentation |
| [chimera-kernel](https://github.com/ChimeraSystem/chimera-kernel) | Mach/BSD kernel, memory management, scheduling, filesystems and drivers |
| [chimera-boot](https://github.com/ChimeraSystem/chimera-boot) | UEFI loader and kernel handoff |
| [chimera-base](https://github.com/ChimeraSystem/chimera-base) | libSystem, dynamic loader, system services and root filesystem configuration |
| [canvas](https://github.com/ChimeraSystem/canvas) | Window server, compositor and desktop shell |
| [chimera-frameworks](https://github.com/ChimeraSystem/chimera-frameworks) | Foundation, AppKit and ChimeraKit |
| [chimera-graphics](https://github.com/ChimeraSystem/chimera-graphics) | DRM, OpenGL and platform adapters |
| [chimera-apps](https://github.com/ChimeraSystem/chimera-apps) | Native desktop applications |
| [chimera-utils](https://github.com/ChimeraSystem/chimera-utils) | Command-line utilities and platform adapters |
| [chimera-assets](https://github.com/ChimeraSystem/chimera-assets) | Branding, wallpapers, icons, fonts and cursors |
| [chimera-host-gpu](https://github.com/ChimeraSystem/chimera-host-gpu) | Host QEMU tools and Virgl/ANGLE/Metal integration |

## Running Chimera

The supported build host is macOS. Once the component checkouts and dependencies
are in place, use the integration repository:

```sh
make build
make run-gui
```

Use `make run-gui-live` to keep a persistent guest disk between launches.

[Build instructions](https://github.com/ChimeraSystem/chimera#build)
· [Host GPU setup](https://github.com/ChimeraSystem/chimera/blob/main/docs/HOST_COCOA_GPU.md)
· [Self-hosting](https://github.com/ChimeraSystem/chimera/blob/main/docs/SELF_HOSTING.md)
· [Bare-metal work](https://github.com/ChimeraSystem/chimera/blob/main/docs/BARE_METAL_TARGET.md)
