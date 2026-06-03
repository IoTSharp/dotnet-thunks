# IoTSharp .NET Runtime Low Glibc Arm32

This package makes `linux-arm` self-contained publish output use IoTSharp-built .NET native artifacts targeting glibc 2.28. It replaces the runtime `.so` files and supplies low-glibc `apphost` templates, so the generated application executable is compatible too.

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

The package is active only for `RuntimeIdentifier=linux-arm` and self-contained publish. Single-file publish is rejected because the runtime `.so` files must be copied as separate files before the app runs.
