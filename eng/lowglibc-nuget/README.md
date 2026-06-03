# IoTSharp .NET Runtime Low Glibc Arm32

This package replaces the native `.so` files in `linux-arm` self-contained publish output with IoTSharp-built .NET runtime native libraries targeting glibc 2.28.

Add the package to an application project:

```xml
<ItemGroup>
  <PackageReference Include="IoTSharp.DotNetRuntime.LowGlibc.Arm32" Version="10.0.0-glibc228.x" PrivateAssets="all" />
</ItemGroup>
```

Publish with:

```bash
dotnet publish -c Release -r linux-arm --self-contained true /p:PublishSingleFile=false
```

The package is active only for `RuntimeIdentifier=linux-arm` and self-contained publish. Single-file publish is rejected because the runtime files must be copied as separate files.
