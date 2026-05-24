# <img src="assets/NSS-128x128.png" align="left" />Nefarius.Shared.PdbUtils

[![.NET](https://github.com/nefarius/Nefarius.Shared.PdbUtils/actions/workflows/build.yml/badge.svg)](https://github.com/nefarius/Nefarius.Shared.PdbUtils/actions/workflows/build.yml)
![Requirements](https://img.shields.io/badge/Requires-.NET%20Standard%202.0%20%2F%20.NET%208%2F9%2F10-blue.svg)
[![NuGet Version](https://img.shields.io/nuget/v/Nefarius.Shared.PdbUtils)](https://www.nuget.org/packages/Nefarius.Shared.PdbUtils/)
[![NuGet](https://img.shields.io/nuget/dt/Nefarius.Shared.PdbUtils)](https://www.nuget.org/packages/Nefarius.Shared.PdbUtils/)

Shared utilities for parsing Microsoft Program Database (PDB) files, based on
[kaitai-pdb](https://github.com/smx-smx/kaitai-pdb). Used internally by
[Nefarius.Utilities.ETW](https://github.com/nefarius/Nefarius.Utilities.ETW) for WPP Software Tracing symbol
resolution.

## Features

- Cross-platform PDB parsing via a [Kaitai Struct](https://kaitai.io/)-generated binary reader
- Extension method to extract the original PDB file name from the DBI stream
- Targets `.NET Standard 2.0`, `.NET 8`, `.NET 9` and `.NET 10`

## Documentation

[Link to API docs](docs/index.md).

## Usage

### Parse a PDB file

```csharp
using Kaitai;
using Nefarius.Shared.PdbUtils.Extensions;

// open and parse the PDB binary
MsPdb pdb = MsPdb.FromFile(@"C:\path\to\my.pdb");

// retrieve the original PDB file name stored in the DBI stream
string? name = pdb.GetOriginalPdbName();
Console.WriteLine(name); // e.g. "my.pdb"
```

## Sources & 3rd party credits

- [kaitai-pdb](https://github.com/smx-smx/kaitai-pdb)
- [kaitai-struct-compiler](https://github.com/nefarius/docker-kaitai-struct-compiler)
- [KaitaiStruct.Runtime.CSharp](https://github.com/kaitai-io/kaitai_struct_csharp_runtime)
- [MinVer](https://github.com/adamralph/minver)
- [PolySharp](https://github.com/Sergio0694/PolySharp)
