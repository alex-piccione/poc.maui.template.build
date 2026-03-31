# MAUI template build

``dotnet build``: ✅  
``dotnet build -c Release``: ✅  
``dotnet restore ; dotnet build -c Release --no-restore``: ‼️  
  
Why dotnet restore + dotnet build fails ?  
(In GitHub actions I usually do that in separate steps: restore + tests + build, that is why I want the _--no-restore_ flag)    

```bash
$ dotnet restore
Restore complete (2,0s)

$ dotnet build --no-restore -c Release
  MauiApp2 net10.0-maccatalyst maccatalyst-x64 succeeded (1,2s) → MauiApp2\bin\Release\net10.0-maccatalyst\maccatalyst-x64\MauiApp2.dll
  MauiApp2 net10.0-ios iossimulator-x64 succeeded (2,2s) → MauiApp2\bin\Release\net10.0-ios\iossimulator-x64\MauiApp2.dll
  MauiApp2 net10.0-maccatalyst maccatalyst-arm64 failed with 1 error(s) (0,1s)
    C:\Program Files\dotnet\sdk\10.0.201\Sdks\Microsoft.NET.Sdk\targets\Microsoft.PackageDependencyResolution.targets(266,5): error NETSDK1047: Assets file 'D:\Programming\Learning\learning.MAUI\poc.maui.template.build\MauiApp2\obj\project.assets.json' doesn't have a target for 'net10.0-maccatalyst/maccatalyst-arm64'. Ensure that restore has run and that you have included 'net10.0-maccatalyst' in the TargetFrameworks for your project. You may also need to include 'maccatalyst-arm64' in your project's RuntimeIdentifiers.
```



