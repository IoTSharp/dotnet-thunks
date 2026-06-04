# IoTSharp Runtime Distribution Matrix

This repository keeps the custom IoTSharp runtime builds aligned across the supported legacy targets:

| Target | Runtime archive | Self-contained publish replacement NuGet |
| --- | --- | --- |
| Linux ARM32 glibc 2.28 | `dotnet-runtime-linux-arm-glibc228-*.tar.gz` | `IoTSharp.DotNetRuntime.LowGlibc.Arm32` |
| Windows XP x86 | `dotnet-runtime-windows-xp-x86-*.zip` | `IoTSharp.DotNetRuntime.WindowsXp.X86` |

Use the runtime archive when you need the CI-built runtime payload directly, for example for manual runtime layout integration, diagnostics, or downstream packaging.

Use the replacement NuGet when an application is published self-contained and should carry the IoTSharp runtime native binaries in its publish directory.

Both replacement packages are active only for their target RID and self-contained publish. They reject `PublishSingleFile=true` because the native runtime files must remain separate in the publish output.
