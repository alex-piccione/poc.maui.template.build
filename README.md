# MAUI template build

Create a Visual Studio project (Visual Studio 2026), selecting the MAUI template.
(for this POC I also checked the "with data" option).

From a shell (I use GitBash on Windows):  
- ``dotnet build``: ✅  
- ``dotnet build -c Release``: ✅  
- ``dotnet restore ; dotnet build -c Release --no-restore``: ‼️  
    
Why dotnet restore + dotnet build --no-restore fails?  
(In GitHub actions I usually do that in separate steps: restore + tests + build, that is why I need the _--no-restore_ flag)    

```bash
$ dotnet build --no-restore -c Release
  MauiApp2 net10.0-maccatalyst maccatalyst-x64 succeeded (1,2s) → MauiApp2\bin\Release\net10.0-maccatalyst\maccatalyst-x64\MauiApp2.dll
  MauiApp2 net10.0-ios iossimulator-x64 succeeded (2,2s) → MauiApp2\bin\Release\net10.0-ios\iossimulator-x64\MauiApp2.dll
  MauiApp2 net10.0-maccatalyst maccatalyst-arm64 failed with 1 error(s) (0,1s)
    C:\Program Files\dotnet\sdk\10.0.201\Sdks\Microsoft.NET.Sdk\targets\Microsoft.PackageDependencyResolution.targets(266,5): error NETSDK1047: Assets file 'D:\Programming\Learning\learning.MAUI\poc.maui.template.build\MauiApp2\obj\project.assets.json' doesn't have a target for 'net10.0-maccatalyst/maccatalyst-arm64'. Ensure that restore has run and that you have included 'net10.0-maccatalyst' in the TargetFrameworks for your project. You may also need to include 'maccatalyst-arm64' in your project's RuntimeIdentifiers.
  MauiApp2 net10.0-android succeeded (2,9s) → MauiApp2\bin\Release\net10.0-android\MauiApp2.dll
  MauiApp2 net10.0-windows10.0.19041.0 win-x64 succeeded (13,1s) → MauiApp2\bin\Release\net10.0-windows10.0.19041.0\win-x64\MauiApp2.dll
```

Image for readability:
<img width="1901" height="200" alt="image" src="https://github.com/user-attachments/assets/b6ed09b7-738d-4948-8f6d-a1c01bff1e20" />


MAUI template:

<img width="1138" height="392" alt="image" src="https://github.com/user-attachments/assets/dbdc7840-297b-4de1-a8d0-8e782105d79f" />

After Updateting the packages, without any other change, the build gives also extra warnings:  

<img width="1452" height="346" alt="image" src="https://github.com/user-attachments/assets/73720d49-864c-4635-bb1f-65f719dd5544" />

<img width="1898" height="1062" alt="image" src="https://github.com/user-attachments/assets/3a86e7ce-8565-492e-a301-4a9f96b2d582" />




