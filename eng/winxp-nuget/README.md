# IoTSharp .NET Runtime Windows XP x86

This package makes `win-x86` self-contained publish output use an IoTSharp-built .NET runtime payload targeting Windows XP x86. It replaces the runtime `.dll` files, including `System.Private.CoreLib.dll`, with files from the same build and supplies Windows XP-compatible `apphost` templates, so the generated application executable is compatible too.

Add the package to an application project:

```xml
<ItemGroup>
  <PackageReference Include="IoTSharp.DotNetRuntime.WindowsXp.X86" Version="10.0.0-winxp.x" PrivateAssets="all" />
</ItemGroup>
```

Publish with:

```bash
dotnet publish -c Release -r win-x86 --self-contained true /p:PublishSingleFile=false
```

The package is active only for `RuntimeIdentifier=win-x86` and self-contained publish. Single-file publish is rejected because the runtime `.dll` files must be copied as separate files before the app runs. Keep the package version aligned with the runtime artifact used for XP testing.
