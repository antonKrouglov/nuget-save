# NuSave

Cache NuGet packages for offline access.

NuSave gives you the ability to cache NuGet packages from nuget.org or
any other source with full dependency tree to your computer for offline use.

Supported platforms: Windows, macOS and Linux.

Written in .NET 7.

## Usage

Check `nusave --help` for usage options.

### Cache a single NuGet package with dependencies

```shell
nusave cache package "Newtonsoft.Json@12.0.3" --targetFrameworks ".NETStandard@1.0,.NETStandard@1.3" --cacheDir "C:\path\to\my-local-feed"
```

The command above will bring all packages that Newtonsoft.Json depend on, and if there are
any duplicates, they will be ignored. NuSave checks for existing `.nupkg` files and
hierarchical package folders.

The combination of NuSave and NuGet.Server gives you the ability to download all
packages needed on your laptop or workstation for offline use.

### Cache multiple NuGet packages from a `.csproj` file

```shell
nusave cache csproj "C:\path\to\project.csproj" --cacheDir "C:\path\to\my-local-feed"
```

### Cache multiple NuGet packages from an `.sln` file

```shell
nusave cache sln "C:\path\to\solution.sln" --cacheDir "C:\path\to\my-local-feed"
```

### Restore and build a solution using NuSave offline cache

```shell
cd C:\path\to\my-solution
dotnet restore --packages C:\path\to\my-local-feed
dotnet build --no-restore
```



MIT License

Copyright (c) 2023 Arash Farahmandi

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.