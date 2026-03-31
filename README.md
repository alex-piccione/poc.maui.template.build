# MAUI template build

``dotnet build``: ✅  
``dotnet build -c Release``: ✅  
``dotnet restore ; dotnet build -c Release --no-restore``: ‼️  
  
Why dotnet restore + dotnet build fails ?
(In GitHub actions I usually do that in separate steps: restore + tests + build, that is why I want the _--no-restore_ flag)    


